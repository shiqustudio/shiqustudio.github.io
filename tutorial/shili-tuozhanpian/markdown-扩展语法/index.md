# Markdown 扩展语法


[![FixIt 0.2.0 | 更改](https://fixit.lruihao.cn/svg/version/0.2.0-changed.zh-cn.min.svg)**FixIt** 主题提供了一些扩展的语法便于你撰写文章。

&lt;!--more--&gt;

## Emoji 支持

这部分内容在 [Emoji 支持页面](https://fixit.lruihao.cn/zh-cn/guides/emoji-support/) 中介绍。

## 数学公式

[![FixIt 0.2.16 | 更改](https://fixit.lruihao.cn/svg/version/0.2.16-changed.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.16)

**FixIt** 基于 [KaTeXKATEX](https://katex.org/) 提供数学公式的支持。

在你的 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中的 `[params.math]` 下面设置属性 `enable = true`, 并在文章的前置参数中设置属性 `math: true` 来启用数学公式的自动渲染。

{{&lt; admonition tip&gt;}}

有一份 [KaTeXKATEX 中支持的 TeXTEX 函数](https://katex.org/docs/supported.html) 清单。

{{&lt; /admonition &gt;}}

{{&lt; admonition &gt;}} 

由于 Hugo 在渲染 Markdown 文档时会根据 `_`/`*`/`&gt;&gt;` 之类的语法生成 HTML 文档， 并且有些转义字符形式的文本内容 (如 `\(`/`\)`/`\[`/`\]`/`\\`) 会自动进行转义处理， 因此需要对这些地方进行额外的转义字符表达来实现自动渲染：

- `_` -&gt; `\_`
- `*` -&gt; `\*`
- `&gt;&gt;` -&gt; `\&gt;&gt;`
- `\(` -&gt; `\\(`
- `\)` -&gt; `\\)`
- `\[` -&gt; `\\[`
- `\]` -&gt; `\\]`
- `\\` -&gt; `\\\\`

**FixIt** 主题支持 [`raw` shortcode](https://fixit.lruihao.cn/zh-cn/documentation/content-management/shortcodes/extended/introduction/#raw) 以避免这些转义字符， 它可以帮助您编写原始数学公式内容。

一个 `raw` 示例：

```markdown
{{&lt; raw &gt;}}行内公式：\(\mathbf{E}=\sum_{i} \mathbf{E}_{i}=\mathbf{E}_{1}&#43;\mathbf{E}_{2}&#43;\mathbf{E}_{3}&#43;\cdots\){{&lt; /raw &gt;}}

{{&lt; raw &gt;}}
公式块：
\[ a=b&#43;c \\ d&#43;e=f \]
{{&lt; /raw &gt;}}
```

 {{&lt; /admonition &gt;}}

呈现的输出效果如下：

{{&lt; raw &gt;}}行内公式：\(\mathbf{E}=\sum_{i} \mathbf{E}_{i}=\mathbf{E}_{1}&#43;\mathbf{E}_{2}&#43;\mathbf{E}_{3}&#43;\cdots\){{&lt; /raw &gt;}}

{{&lt; raw &gt;}}
公式块：
\[ a=b&#43;c \\ d&#43;e=f \]
{{&lt; /raw &gt;}}

### 行内公式

默认的行内公式分割符有：

- `$ ... $`
- `\( ... \)` (转义的: `\\( ... \\)`)

例如:

```tex
$c = \pm\sqrt{a^2 &#43; b^2}$ 和 \\(f(x)=\int_{-\infty}^{\infty} \hat{f}(\xi) e^{2 \pi i \xi x} d \xi\\)
```

呈现的输出效果如下：

$c = \pm\sqrt{a^2 &#43; b^2}$ 和 \\(f(x)=\int_{-\infty}^{\infty} \hat{f}(\xi) e^{2 \pi i \xi x} d \xi\\)

### 公式块

默认的公式块分割符有：

- `$$ ... $$`
- `\[ ... \]` (转义的：`\\[ ... \\]`)
- `\begin{equation} ... \end{equation}` (不编号的：`\begin{equation*} ... \end{equation*}`)
- `\begin{align} ... \end{align}` (不编号的：`\begin{align*} ... \end{align*}`)
- `\begin{alignat} ... \end{alignat}` (不编号的：`\begin{alignat*} ... \end{alignat*}`)
- `\begin{gather} ... \end{gather}` (不编号的：`\begin{gather*} ... \end{gather*}`)
- `\begin{CD} ... \end{CD}`

{{&lt; admonition warning &gt;}}

当公式块中存在换行时，请谨慎开启 `goldmark.renderer.hardWraps`，设置为 true，Goldmark 会将换行符呈现为 `&lt;br&gt;` 元素。

{{&lt; /admonition &gt;}}

例如：

```tex
$$ c = \pm\sqrt{a^2 &#43; b^2} $$

\\[ f(x)=\int_{-\infty}^{\infty} \hat{f}(\xi) e^{2 \pi i \xi x} d \xi \\]

\begin{equation*}
  \rho \frac{\mathrm{D} \mathbf{v}}{\mathrm{D} t}=\nabla \cdot \mathbb{P}&#43;\rho \mathbf{f}
\end{equation*}

\begin{equation}
  \mathbf{E}=\sum_{i} \mathbf{E}\_{i}=\mathbf{E}\_{1}&#43;\mathbf{E}\_{2}&#43;\mathbf{E}_{3}&#43;\cdots
\end{equation}

\begin{align}
  a&amp;=b&#43;c \\\\
  d&#43;e&amp;=f
\end{align}

\begin{alignat}{2}
   10&amp;x&#43;&amp;3&amp;y = 2 \\\\
   3&amp;x&#43;&amp;13&amp;y = 4
\end{alignat}

\begin{gather}
   a=b \\\\
   e=b&#43;c
\end{gather}

\begin{CD}
   A @&gt;a\&gt;&gt; B \\\\
@VbVV @AAcA \\\\
   C @= D
\end{CD}
```

呈现的输出效果如下：

{{&lt; admonition failure &gt;}} 

​	依据警告调整，暂未找到合适方法

{{&lt; /admonition &gt;}}

{{&lt; admonition tip&gt;}}

你可以在 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中自定义行内公式和公式块的分割符。

{{&lt; /admonition &gt;}}

### Copy-tex

**[Copy-tex](https://github.com/Khan/KaTeX/tree/master/contrib/copy-tex)** 是一个 **KaTeXKATEX** 的插件。

通过这个扩展，在选择并复制 KaTeXKATEX 渲染的公式时，会将其 LaTeXLATEX 源代码复制到剪贴板。

在你的 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中的 `[params.math]` 下面设置属性 `copyTex = true` 来启用 Copy-tex。

选择并复制上一节中渲染的公式，可以发现复制的内容为 LaTeX 源代码。

### mhchem

**[mhchem](https://github.com/Khan/KaTeX/tree/master/contrib/mhchem)** 是一个 **KaTeXKATEX** 的插件。

通过这个扩展，你可以在文章中轻松编写漂亮的化学方程式。

在你的 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 中的 `[params.math]` 下面设置属性 `mhchem = true` 来启用 mhchem。



---

> 作者:   
> URL: http://localhost:1313/tutorial/shili-tuozhanpian/markdown-%E6%89%A9%E5%B1%95%E8%AF%AD%E6%B3%95/  
> 转载 URL: https://fixit.lruihao.cn/zh-cn/documentation/content-management/markdown-syntax/extended/
