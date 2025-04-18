# 扩展 Shortcode - Bilibili


[![FixIt 0.2.0 | 更改](https://fixit.lruihao.cn/svg/version/0.2.0-changed.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.0)

`bilibili` shortcode 提供了一个内嵌的用来播放 bilibili 视频的响应式播放器。

&lt;!--more--&gt;

如果视频只有一个部分，则仅需要视频的 BV `id`, 例如：

```
https://www.bilibili.com/video/BV1Sx411T7QQ
```

一个 `bilibili` 示例：

```go-html-template
{{&lt;/* bilibili BV1Sx411T7QQ */&gt;}}
或者
{{&lt;/* bilibili id=BV1Sx411T7QQ */&gt;}}
```

{{&lt; bilibili BV1Sx411T7QQ &gt;}}

如果视频包含多个部分，则除了视频的 BV `id` 之外，还需要 `p`, 默认值为 `1`, 例如：

```
https://www.bilibili.com/video/BV1TJ411C7An?p=3
```

```go-html-template
{{&lt;/* bilibili BV1TJ411C7An 3 */&gt;}}
或者
{{&lt;/* bilibili id=BV1TJ411C7An p=3 */&gt;}}
```

呈现的输出效果如下：

{{&lt; bilibili BV1TJ411C7An 3 &gt;}}


---

> 作者:   
> URL: http://localhost:1313/tutorial/shili-tuozhanpian/%E6%89%A9%E5%B1%95-shortcode-bilibili/  
> 转载 URL: https://fixit.lruihao.cn/zh-cn/documentation/content-management/shortcodes/extended/bilibili/
