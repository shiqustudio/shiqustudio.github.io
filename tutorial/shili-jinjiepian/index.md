# 进阶篇


探索 Hugo - **FixIt** 主题的的进阶使用。

&lt;!--more--&gt;

## 自定义样式

[![FixIt 0.2.8 | 更改](https://fixit.lruihao.cn/svg/version/0.2.8-changed.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.8)

{{&lt; admonition &gt;}} 

Hugo **extended** 版本对于自定义样式是必需的。

通过定义自定义 `.scss` 样式文件，**FixIt** 主题支持可配置的样式。

包含自定义 `.scss` 样式文件的目录相对于 **你的项目根目录** 的路径为 `assets/css`。

在 `assets/css/_override.scss` 中，你可以覆盖 `themes/FixIt/assets/css/_variables.scss` 中的变量以自定义样式。

 {{&lt; /admonition &gt;}}

这是一个例子：

```scss
@import url(&#39;https://fonts.googleapis.com/css?family=Fira&#43;Mono:400,700&amp;display=swap&amp;subset=latin-ext&#39;);
$code-font-family: Fira Mono, Source Code Pro, Menlo, Consolas, Monaco, monospace;
```

在 `assets/css/_custom.scss` 中，你可以添加一些 CSS 样式代码以自定义样式。

### 页面宽度

[![FixIt 0.2.13 | 新增](https://fixit.lruihao.cn/svg/version/0.2.13-new.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.13)

FixIt 主题提供了页面宽度配置选项 `pageStyle` 并提供三种选项。

- **narrow** 保留 `&lt;v0.2.13` 页面目录宽度比
- **normal** 新的默认页面目录宽度比
- **wide** 较大的页面目录宽度比

另外，你还可以在 `assets/css/_custom.scss` 中，自定义 `pageStyle` 值

例如： `pageStyle=&#34;custom&#34;`

```scss
@media only screen and (min-width: 1441px) {
  [data-page-style=&#39;custom&#39;] {
    .page {
      width: 70%;
    }

    aside {
      width: 15%;
    }
  }
}

@media only screen and (max-width: 1440px) {
  [data-page-style=&#39;custom&#39;] {
    .page {
      width: 60%;
    }

    aside {
      width: 20%;
    }
  }
}

@media only screen and (max-width: 1200px) {
  [data-page-style=&#39;custom&#39;] {
    .page {
      width: 56%;
    }

    aside {
      width: 22%;
    }
  }
}
```

### 打印样式

[![FixIt 0.2.13 | 新增](https://fixit.lruihao.cn/svg/version/0.2.13-new.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.13)

在 FixIt 主题中，提供有三个打印视图相关的 CSS 类

- `page-break-before` 在元素之前插入分页符
- `page-break-after` 在元素之后插入分页符
- `print-d-none` 在打印视图中隐藏元素

下面是一个简单的例子：

```html
&lt;div class=&#34;page-break-before&#34;&gt;&lt;/div&gt;
&lt;div class=&#34;page-break-after&#34;&gt;&lt;/div&gt;
&lt;div class=&#34;print-d-none&#34;&gt;
  您希望在打印视图中隐藏的某些内容写在此处。
&lt;/div&gt;
```

如果设置 `goldmark.parser.attribute.block` 为 `true`，你也可以这样用：

```markdown
{.page-break-before}
{.page-break-after}

您希望在打印视图中隐藏的某些内容写在此处。
{.print-d-none}
```

## 自定义脚本

[![FixIt 0.2.16 | 新增](https://fixit.lruihao.cn/svg/version/0.2.16-new.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.16)

包含自定义脚本文件 `custom.js` 的目录相对于 **你的项目根目录** 的路径为 `assets/js`。

如果脚本文件 `assets/js/custom.js` 存在，它将在每篇文章和页面的末尾执行。

## 自定义模板

Hugo 允许您通过覆盖主题模板来改造主题，例如：您可以创建 `layouts/404.html` 文件以覆盖 `themes/FixIt/layouts/404.html`，从而实现自定义 FixIt 主题 404 页面模板的需求。

但是，对于主题的大多数模板，FixIt 通常不建议您这样做，因为这样可能会导致未来升级主题困难。

为了避免升级冲突问题，基于这一特性，FixIt 主题在常用的位置开放了几个空的模板以供用户客制化，详见 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中的 `params.customFilePath` 参数。

例如，FixIt 主题文档站点通过创建 `layouts/partials/custom/profile.html` 自定义了首页的 profile 部分。

首先，启用自定义文件路径参数：

```toml
[params.customFilePath]
  profile = &#34;custom/profile.html&#34;
```

然后，自定义模板：

## PWA 支持

这部分内容在 [PWA 支持页面](https://fixit.lruihao.cn/zh-cn/guides/pwa-support/) 中介绍。


---

> 作者:   
> URL: http://localhost:1313/tutorial/shili-jinjiepian/  
> 转载 URL: https://fixit.lruihao.cn/zh-cn/documentation/advanced/
