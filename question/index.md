# 常见问答


&gt; 本文档记录一些常见的问答，主要来自 [GitHub Discussions](https://github.com/shiqustudio/giscus/discussions) 和 QQ 群：`864217652`。

&lt;!--more--&gt;

{{&lt; admonition question &#34;**为什么不支持早期版本的 Hugo？**&#34; false&gt;}}

由于 [函数 `path.Clean`](https://gohugo.io/functions/path.clean/) 在 [Hugo 发行版 v0.89.0](https://github.com/gohugoio/hugo/releases/tag/v0.89.0) 中被引入的，因此本主题只支持不低于 **0.89.0** 的 Hugo 版本。

{{&lt; /admonition &gt;}}

{{&lt; admonition question &#34;**为什么推荐使用 Hugo extended 版本？**&#34; false&gt;}}

由于这个主题的一些特性需要将 SCSS 转换为 CSS, 推荐使用 Hugo **extended** 版本来获得更好的使用体验。

{{&lt; /admonition &gt;}}

{{&lt; admonition question &#34;**如何切换 Hugo 的运行环境？**&#34; false&gt;}}

`hugo server` 的默认运行环境是 `development`, 而 `hugo` 的默认运行环境是 `production`。

由于本地 `development` 环境的限制， **评论系统** , **CDN** 和 **fingerprint** 不会在 `development` 环境下启用。

你可以使用 `hugo server -e production` 命令来开启这些特性。

{{&lt; /admonition &gt;}}

{{&lt; admonition question &#34;**怎样选择搜索引擎？**&#34; false&gt;}}

以下是两种搜索引擎的对比：

- `fuse`: 简单，无需同步 `index.json`, 没有 `contentLength` 的限制，性能高
- `lunr`: 简单，无需同步 `index.json`, 没有 `contentLength` 的限制，但占用带宽大且性能低（特别是中文需要一个较大的分词依赖库）
- `algolia`: 高性能并且占用带宽低，但需要同步 `index.json` 且有 `contentLength` 的限制

[![FixIt 0.2.3 | 新增](https://fixit.lruihao.cn/svg/version/0.2.3-new.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.3) 文章内容被 `h2` 和 `h3` HTML 标签切分来提高查询效果并且基本实现全文搜索。 `contentLength` 用来限制 `h2` 和 `h3` HTML 标签开头的内容部分的最大长度。

{{&lt; /admonition &gt;}}

{{&lt; admonition question &#34;**其他问题？**&#34; false&gt;}}

{{&lt; style &#34;min-height: 30px;&#34; &gt;}}

{{&lt; typeit code=javascript &gt;}}

欢迎留言补充......

{{&lt; /typeit &gt;}}

{{&lt; /style &gt;}}

{{&lt; /admonition &gt;}}

没找到你的问题？加入 [讨论&lt;i class=&#34;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&#34; aria-hidden=&#34;true&#34;&gt;&lt;/i&gt;](https://github.com/orgs/hugo-fixit/discussions/new/choose) 或者 QQ 群：`864217652`。



---

> 作者:   
> URL: http://localhost:1313/question/  

