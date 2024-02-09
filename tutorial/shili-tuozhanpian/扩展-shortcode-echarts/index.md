# 扩展 Shortcode - echarts


[![FixIt 0.2.0 | 更改](https://fixit.lruihao.cn/svg/version/0.2.0-changed.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.0)

`echarts` shortcode 使用 [ECharts](https://echarts.apache.org/) 库提供数据可视化的功能。

&lt;!--more--&gt;

- **ECharts** 是一个帮助你生成交互式数据可视化的库。

  ECharts 提供了常规的 [折线图](https://echarts.apache.org/zh/option.html#series-line), [柱状图](https://echarts.apache.org/zh/option.html#series-line), [散点图](https://echarts.apache.org/zh/option.html#series-scatter), [饼图](https://echarts.apache.org/zh/option.html#series-pie), [K 线图](https://echarts.apache.org/zh/option.html#series-candlestick), 用于统计的 [盒形图][boxplot], 用于地理数据可视化的 [地图](https://echarts.apache.org/zh/option.html#series-map), [热力图](https://echarts.apache.org/zh/option.html#series-heatmap), [线图](https://echarts.apache.org/zh/option.html#series-lines), 用于关系数据可视化的 [关系图](https://echarts.apache.org/zh/option.html#series-graph), [treemap](https://echarts.apache.org/zh/option.html#series-treemap), [旭日图](https://echarts.apache.org/zh/option.html#series-sunburst), 多维数据可视化的 [平行坐标](https://echarts.apache.org/zh/option.html#series-parallel), 还有用于 BI 的 [漏斗图](https://echarts.apache.org/zh/option.html#series-funnel), [仪表盘](https://echarts.apache.org/zh/option.html#series-gauge), 并且支持图与图之间的混搭。
  
  只需在 `echarts` shortcode 中以 `JSON`/`YAML`/`TOML` 格式插入 ECharts 选项即可。
  
  一个 `JSON` 格式的 `echarts` 示例:
  
  {{&lt; echarts &gt;}}
  {
    &#34;title&#34;: {
      &#34;text&#34;: &#34;折线统计图&#34;,
      &#34;top&#34;: &#34;2%&#34;,
      &#34;left&#34;: &#34;center&#34;
    },
    &#34;tooltip&#34;: {
      &#34;trigger&#34;: &#34;axis&#34;
    },
    &#34;legend&#34;: {
      &#34;data&#34;: [&#34;邮件营销&#34;, &#34;联盟广告&#34;, &#34;视频广告&#34;, &#34;直接访问&#34;, &#34;搜索引擎&#34;],
      &#34;top&#34;: &#34;10%&#34;
    },
    &#34;grid&#34;: {
      &#34;left&#34;: &#34;5%&#34;,
      &#34;right&#34;: &#34;5%&#34;,
      &#34;bottom&#34;: &#34;5%&#34;,
      &#34;top&#34;: &#34;20%&#34;,
      &#34;containLabel&#34;: true
    },
    &#34;toolbox&#34;: {
      &#34;feature&#34;: {
        &#34;saveAsImage&#34;: {
          &#34;title&#34;: &#34;保存为图片&#34;
        }
      }
    },
    &#34;xAxis&#34;: {
      &#34;type&#34;: &#34;category&#34;,
      &#34;boundaryGap&#34;: false,
      &#34;data&#34;: [&#34;周一&#34;, &#34;周二&#34;, &#34;周三&#34;, &#34;周四&#34;, &#34;周五&#34;, &#34;周六&#34;, &#34;周日&#34;]
    },
    &#34;yAxis&#34;: {
      &#34;type&#34;: &#34;value&#34;
    },
    &#34;series&#34;: [
      {
        &#34;name&#34;: &#34;邮件营销&#34;,
        &#34;type&#34;: &#34;line&#34;,
        &#34;stack&#34;: &#34;总量&#34;,
        &#34;data&#34;: [120, 132, 101, 134, 90, 230, 210]
      },
      {
        &#34;name&#34;: &#34;联盟广告&#34;,
        &#34;type&#34;: &#34;line&#34;,
        &#34;stack&#34;: &#34;总量&#34;,
        &#34;data&#34;: [220, 182, 191, 234, 290, 330, 310]
      },
      {
        &#34;name&#34;: &#34;视频广告&#34;,
        &#34;type&#34;: &#34;line&#34;,
        &#34;stack&#34;: &#34;总量&#34;,
        &#34;data&#34;: [150, 232, 201, 154, 190, 330, 410]
      },
      {
        &#34;name&#34;: &#34;直接访问&#34;,
        &#34;type&#34;: &#34;line&#34;,
        &#34;stack&#34;: &#34;总量&#34;,
        &#34;data&#34;: [320, 332, 301, 334, 390, 330, 320]
      },
      {
        &#34;name&#34;: &#34;搜索引擎&#34;,
        &#34;type&#34;: &#34;line&#34;,
        &#34;stack&#34;: &#34;总量&#34;,
        &#34;data&#34;: [820, 932, 901, 934, 1290, 1330, 1320]
      }
    ]
  }
  {{&lt; /echarts &gt;}}
  
  ```yaml
  {{&lt; echarts &gt;}}
  title:
      text: 折线统计图
      top: 2%
      left: center
  tooltip:
      trigger: axis
  legend:
      data:
          - 邮件营销
          - 联盟广告
          - 视频广告
          - 直接访问
          - 搜索引擎
      top: 10%
  grid:
      left: 5%
      right: 5%
      bottom: 5%
      top: 20%
      containLabel: true
  toolbox:
      feature:
          saveAsImage:
              title: 保存为图片
  xAxis:
      type: category
      boundaryGap: false
      data:
          - 周一
          - 周二
          - 周三
          - 周四
          - 周五
          - 周六
          - 周日
  yAxis:
      type: value
  series:
      - name: 邮件营销
        type: line
        stack: 总量
        data:
            - 120
            - 132
            - 101
            - 134
            - 90
            - 230
            - 210
      - name: 联盟广告
        type: line
        stack: 总量
        data:
            - 220
            - 182
            - 191
            - 234
            - 290
            - 330
            - 310
      - name: 视频广告
        type: line
        stack: 总量
        data:
            - 150
            - 232
            - 201
            - 154
            - 190
            - 330
            - 410
      - name: 直接访问
        type: line
        stack: 总量
        data:
            - 320
            - 332
            - 301
            - 334
            - 390
            - 330
            - 320
      - name: 搜索引擎
        type: line
        stack: 总量
        data:
            - 820
            - 932
            - 901
            - 934
            - 1290
            - 1330
            - 1320
  {{&lt; /echarts &gt;}}
  ```

```toml
{{&lt; echarts &gt;}}
[title]
text = &#34;折线统计图&#34;
top = &#34;2%&#34;
left = &#34;center&#34;

[tooltip]
trigger = &#34;axis&#34;

[legend]
data = [
  &#34;邮件营销&#34;,
  &#34;联盟广告&#34;,
  &#34;视频广告&#34;,
  &#34;直接访问&#34;,
  &#34;搜索引擎&#34;
]
top = &#34;10%&#34;

[grid]
left = &#34;5%&#34;
right = &#34;5%&#34;
bottom = &#34;5%&#34;
top = &#34;20%&#34;
containLabel = true

[toolbox]
[toolbox.feature]
[toolbox.feature.saveAsImage]
title = &#34;保存为图片&#34;

[xAxis]
type = &#34;category&#34;
boundaryGap = false
data = [
  &#34;周一&#34;,
  &#34;周二&#34;,
  &#34;周三&#34;,
  &#34;周四&#34;,
  &#34;周五&#34;,
  &#34;周六&#34;,
  &#34;周日&#34;
]

[yAxis]
type = &#34;value&#34;

[[series]]
name = &#34;邮件营销&#34;
type = &#34;line&#34;
stack = &#34;总量&#34;
data = [
  120.0,
  132.0,
  101.0,
  134.0,
  90.0,
  230.0,
  210.0
]

[[series]]
name = &#34;联盟广告&#34;
type = &#34;line&#34;
stack = &#34;总量&#34;
data = [
  220.0,
  182.0,
  191.0,
  234.0,
  290.0,
  330.0,
  310.0
]

[[series]]
name = &#34;视频广告&#34;
type = &#34;line&#34;
stack = &#34;总量&#34;
data = [
  150.0,
  232.0,
  201.0,
  154.0,
  190.0,
  330.0,
  410.0
]

[[series]]
name = &#34;直接访问&#34;
type = &#34;line&#34;
stack = &#34;总量&#34;
data = [
  320.0,
  332.0,
  301.0,
  334.0,
  390.0,
  330.0,
  320.0
]

[[series]]
name = &#34;搜索引擎&#34;
type = &#34;line&#34;
stack = &#34;总量&#34;
data = [
  820.0,
  932.0,
  901.0,
  934.0,
  1290.0,
  1330.0,
  1320.0
]
{{&lt; /echarts &gt;}}
```

`echarts` shortcode 还有以下命名参数:

- **width** *[可选]* (**第一个**位置参数)

  [![FixIt 0.2.0 | 新增](https://fixit.lruihao.cn/svg/version/0.2.0-new.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.0) 数据可视化的宽度，默认值是 `100%`

- **height** *[可选]* (**第二个**位置参数)

  [![FixIt 0.2.0 | 新增](https://fixit.lruihao.cn/svg/version/0.2.0-new.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.0) 数据可视化的高度，默认值是 `30rem`


---

> 作者:   
> URL: https://blog.funvip.live/tutorial/shili-tuozhanpian/%E6%89%A9%E5%B1%95-shortcode-echarts/  
> 转载 URL: https://fixit.lruihao.cn/zh-cn/documentation/content-management/shortcodes/extended/echarts/
