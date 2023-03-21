# 扩展 Shortcode - mapbox


[![FixIt 0.2.0 | 新增](https://fixit.lruihao.cn/svg/version/0.2.0-new.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.0)

`mapbox` shortcode 使用 [Mapbox GL JS](https://docs.mapbox.com/mapbox-gl-js) 库提供互动式地图的功能。

[Mapbox GL JS](https://docs.mapbox.com/mapbox-gl-js) 是一个 JavaScript 库，它使用 WebGL, 以 [vector tiles](https://docs.mapbox.com/help/glossary/vector-tiles/) 和 [Mapbox styles](https://docs.mapbox.com/mapbox-gl-js/style-spec/) 为来源，将它们渲染成互动式地图。

`mapbox` shortcode 有以下命名参数来使用 Mapbox GL JS:

- **lng** *[必需]*（**第一个**位置参数）

  地图初始中心点的经度，以度为单位。

- **lat** *[必需]*（**第二个**位置参数）

  地图初始中心点的纬度，以度为单位。

- **zoom** *[可选]*（**第三个**位置参数）

  地图的初始缩放级别，默认值是 `10`。

- **marked** *[可选]*（**第四个**位置参数）

  是否在地图的初始中心点添加图钉，默认值是 `true`。

- **light-style** *[可选]*（**第五个**位置参数）

  浅色主题的地图样式，默认值是 [前置参数](https://fixit.lruihao.cn/zh-cn/documentation/content-management/introduction/#front-matter) 或者 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中设置的值。

- **dark-style** *[可选]*（**第六个**位置参数）

  深色主题的地图样式，默认值是 [前置参数](https://fixit.lruihao.cn/zh-cn/documentation/content-management/introduction/#front-matter) 或者 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中设置的值。

- **navigation** *[可选]*

  是否添加 [NavigationControl](https://docs.mapbox.com/mapbox-gl-js/api#navigationcontrol), 默认值是 [前置参数](https://fixit.lruihao.cn/zh-cn/documentation/content-management/introduction/#front-matter) 或者 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中设置的值。

- **geolocate** *[可选]*

  是否添加 [GeolocateControl](https://docs.mapbox.com/mapbox-gl-js/api#geolocatecontrol), 默认值是 [前置参数](https://fixit.lruihao.cn/zh-cn/documentation/content-management/introduction/#front-matter) 或者 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中设置的值。

- **scale** *[可选]*

  是否添加 [ScaleControl](https://docs.mapbox.com/mapbox-gl-js/api#scalecontrol), 默认值是 [前置参数](https://fixit.lruihao.cn/zh-cn/documentation/content-management/introduction/#front-matter) 或者 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中设置的值。

- **fullscreen** *[可选]*

  是否添加 [FullscreenControl](https://docs.mapbox.com/mapbox-gl-js/api#fullscreencontrol), 默认值是 [前置参数](https://fixit.lruihao.cn/zh-cn/documentation/content-management/introduction/#front-matter) 或者 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中设置的值。

- **width** *[可选]*

  地图的宽度，默认值是 `100%`。

- **height** *[可选]*

  地图的高度，默认值是 `20rem`。

一个简单的 `mapbox` 示例：

```go-html-template
{{< mapbox 113.953277 22.559102 11 >}}
或者
{{< mapbox lng=113.953277 lat=22.559102 zoom=11 >}}
```

呈现的输出效果如下：

{{< mapbox 113.953277 22.559102 11 >}}

一个带有自定义样式的 `mapbox` 示例：

```go-html-template
{{< mapbox -122.252 37.453 10 false "mapbox://styles/mapbox/streets-zh-v1" >}}
或者
{{< mapbox lng=-122.252 lat=37.453 zoom=10 marked=false light-style="mapbox://styles/mapbox/streets-zh-v1" >}}
```

呈现的输出效果如下：

{{< mapbox -122.252 37.453 10 false "mapbox://styles/mapbox/streets-zh-v1" >}}


---

> 作者: [xucong](https://shiqustudio.github.io/)  
> URL: https://shiqustudio.github.io/shili-tuozhanpian/%E6%89%A9%E5%B1%95-shortcode-mapbox/  

