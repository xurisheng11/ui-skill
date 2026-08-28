# 实践样例：指标监控图表（ECharts）

使用 Ajax 拉取监控数据，通过 ECharts 渲染折线图的完整示例。

## 前端 DOM 占位符

在 `build` 方法中用 `markupItem` 创建 div 占位符：

```typescript
BaseUI.container(
  {
    '#type': 'aws_key_value_pairs',
    '#columns': 3,
    '#items': Object.values({
      cpuMonitor:         BaseUI.cardItem('', BaseUI.markupItem('<div id="cpu_monitor"></div>')),
      memoryMonitor:      BaseUI.cardItem('', BaseUI.markupItem('<div id="memory_monitor"></div>')),
      concurrencyMonitor: BaseUI.cardItem('', BaseUI.markupItem('<div id="concurrency_monitor"></div>')),
    }),
  },
  '指标监控',
  {
    // 时间范围选择控件（分段控件）
    chart_days: BaseUI.segmentedControl(
      [
        { text: '5分钟',  id: '5m'  },
        { text: '10分钟', id: '10m' },
        { text: '30分钟', id: '30m' },
        { text: '1小时',  id: '1h'  },
        { text: '2小时',  id: '2h'  },
        { text: '5小时',  id: '5h'  },
      ],
      '5m',
    )
  }
)
```

## JS 注入代码（完整模板）

```javascript
useEffect(() => {
  // 时间范围映射
  var rangeMap = { '5m': 5*60, '10m': 10*60, '30m': 30*60, '1h': 60*60, '2h': 2*60*60, '5h': 5*60*60 };
  var rangeSeconds = rangeMap[value_chart_days] || 5 * 60;
  var end = Math.floor(Date.now() / 1000);
  var start = end - rangeSeconds;

  // 渲染单折线图
  function renderChart(elementId, title, unit, items) {
    var maxTry = 20, tried = 0;
    var timer = setInterval(function() {
      var box = document.getElementById(elementId);
      tried++;
      if (!box) { if (tried >= maxTry) clearInterval(timer); return; }
      clearInterval(timer);
      box.style.height = '300px';
      var chart = echarts.init(box);
      chart.setOption({
        title: { text: title, left: 'center', textStyle: { fontSize: 14, color: '#333' } },
        tooltip: { trigger: 'axis' },
        xAxis: {
          type: 'category',
          data: items.map(function(d) {
            var date = new Date(d.timestamp * 1000);
            return ('0'+date.getHours()).slice(-2)+':'+('0'+date.getMinutes()).slice(-2)+':'+('0'+date.getSeconds()).slice(-2);
          })
        },
        yAxis: { type: 'value', name: unit },
        series: [{
          name: title,
          data: items.map(function(d) { return parseFloat(d.value).toFixed(4); }),
          type: 'line',
          smooth: false,
          itemStyle: { color: '#5b8ff9' },
          lineStyle: { color: '#5b8ff9', width: 2 }
        }]
      });
      window.addEventListener('resize', function() { chart.resize(); });
    }, 200);
  }

  // 拉取 CPU 数据
  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: { method: 'get', url: '{LUBAN_HOST}/module/metrics/cpu?start=' + start + '&end=' + end + '&id=TARGET_ID' },
    dataType: 'json',
    success: function(response) {
      var items = (response || []).length ? response : [{ timestamp: Math.floor(Date.now()/1000), value: '0' }];
      renderChart('cpu_monitor', 'CPU 使用', 'm', items);
    }
  });

  // 拉取内存数据
  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: { method: 'get', url: '{LUBAN_HOST}/module/metrics/memory?start=' + start + '&end=' + end + '&id=TARGET_ID' },
    dataType: 'json',
    success: function(response) {
      var items = (response || []).length ? response : [{ timestamp: Math.floor(Date.now()/1000), value: '0' }];
      renderChart('memory_monitor', '内存使用', 'Mi', items);
    }
  });

}, [value_chart_days, value_module_tabs]);  // 时间范围或 Tab 切换时重绘
```

## 后端 API 接口（Controller）

```typescript
// 数据格式：[{ timestamp: 秒级时间戳, value: '数值字符串' }]
@Get('/metrics/cpu')
public async getMetricsCpu(
  @Query('id') id: string,
  @Query('start') start: string,
  @Query('end') end: string,
) {
  return await this.get(`${Base.ROOT}/modules/${id}/metrics/cpu?start=${start}&end=${end}`);
}
```

## 多折线图（适用于并发等多维指标）

```javascript
function renderMultiLineChart(elementId, title, seriesList) {
  // seriesList: [{ name: '线条名', color: '#hex', items: [{timestamp, value}] }]
  var maxTry = 20, tried = 0;
  var timer = setInterval(function() {
    var box = document.getElementById(elementId);
    tried++;
    if (!box) { if (tried >= maxTry) clearInterval(timer); return; }
    clearInterval(timer);
    box.style.height = '300px';
    var chart = echarts.init(box);
    var xData = (seriesList[0] && seriesList[0].items || []).map(function(d) {
      var date = new Date(d.timestamp * 1000);
      return ('0'+date.getHours()).slice(-2)+':'+('0'+date.getMinutes()).slice(-2)+':'+('0'+date.getSeconds()).slice(-2);
    });
    chart.setOption({
      title: { text: title, left: 'center' },
      tooltip: { trigger: 'axis' },
      legend: { bottom: 0, data: seriesList.map(function(s) { return s.name; }) },
      xAxis: { type: 'category', data: xData },
      yAxis: { type: 'value' },
      series: seriesList.map(function(s) {
        return {
          name: s.name,
          data: s.items.map(function(d) { return parseFloat(d.value).toFixed(4); }),
          type: 'line',
          itemStyle: { color: s.color },
          lineStyle: { color: s.color, width: 2 }
        };
      })
    });
    window.addEventListener('resize', function() { chart.resize(); });
  }, 200);
}

// 调用示例（三条折线）
renderMultiLineChart('concurrency_monitor', '并发请求数', [
  { name: '总并发数',   color: '#5b8ff9', items: totalItems    },
  { name: '5xx 并发数', color: '#cf1322', items: error5xxItems },
  { name: '4xx 并发数', color: '#fa8c16', items: error4xxItems }
]);
```
