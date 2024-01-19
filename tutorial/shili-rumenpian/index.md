# 入门篇


探索 Hugo - **FixIt** 主题的的基础知识和背后的核心概念。

&lt;!--more--&gt;

## 安装方式

{{&lt; link &#34;https://github.com/hugo-fixit/FixIt&#34; &#34;FixIt 主题的仓库&#34; &#34;source of FixIt Theme&#34; true &gt;}}

实际上有多种方式可以快速安装主题，选择其中 **一种** 即可（推荐 [Git 子模块](https://fixit.lruihao.cn/zh-cn/documentation/basics/#git-submodule) 或者 [Hugo 模块](https://fixit.lruihao.cn/zh-cn/documentation/basics/#hugo-module)）。

### 手动下载

你可以下载主题的 [最新版本 .zip 文件](https://github.com/hugo-fixit/FixIt/releases) 并且解压放到 `themes` 目录。

### Git 克隆

或者，也可以直接把这个主题克隆到 `themes` 目录：

```bash
git clone https://github.com/hugo-fixit/FixIt.git themes/FixIt
```

### Git 子模块

{{&lt; link &#34;https://github.com/hugo-fixit/hugo-fixit-blog&#34; &#34;基于 Git 子模块的快速入门模板&#34; &#34;source of FixIt Theme&#34; true &gt;}}

另外，在您的项目目录初始化一个空的 Git 存储库，将 [FixIt](https://github.com/hugo-fixit/FixIt) 主题克隆到 `themes` 目录中，将其作为 [Git 子模块](https://git-scm.com/book/en/v2/Git-Tools-Submodules) 添加到您的项目中。

```bash
git init 
git submodule add https://github.com/hugo-fixit/FixIt.git themes/FixIt
```

如果你想使用 `dev` 分支上的版本，可以使用以下命令：

```bash
 git submodule add -b dev https://github.com/hugo-fixit/FixIt.git themes/FixIt
```

或者将子模块分支从 `master` 切换到 `dev`：

```bash
 git submodule set-branch -b dev themes/FixIt
```



### Hugo 模块

{{&lt;link &#34;https://github.com/hugo-fixit/hugo-fixit-blog-go&#34; &#34;基于 Hugo 模块的快速入门模板&#34; &#34;&#34; true &gt;}}

&gt; 以这种方式，无需要在 `config.toml` 中配置 `theme = &#34;FixIt&#34;`。

将 [Hugo 模块](https://gohugo.io/hugo-modules/) 用于主题的最简单方法是将其导入配置中。请参阅 [使用 Hugo 模块](https://gohugo.io/hugo-modules/use-modules/)。

1. 初始化 Hugo 模块系统：`hugo mod init github.com/&lt;your_user&gt;/&lt;your_project&gt;`

2. 导入主题：

   ```toml
   [module]
     [[module.imports]]
       path = &#34;github.com/hugo-fixit/FixIt&#34;
   ```

   

## 完整配置

在开始配置之前，建议您执行以下命令，将主题的默认 [config.toml](https://github.com/hugo-fixit/FixIt/blob/master/config.toml) 复制到您的项目中：

```bash
mv config.toml config.old.toml
cp themes/FixIt/config.toml config.toml
```

### 菜单配置

Hugo 有一个简单而强大的 [菜单系统](https://gohugo.io/content-management/menus/)。

根据 Hugo 提供的接口，FixIt 主题只实现了部分功能，这足以满足大多数人的需求，也让用户在使用上更加简单。

下面是一个完整的菜单项配置：

```bash
[menu]
  [[menu.main]]
    identifier = &#34;&#34;
    #  父级菜单项的标识符 (identifier)
    parent = &#34;&#34;
    # 你可以在名称（允许 HTML 格式）之前添加其他信息，例如图标
    pre = &#34;&#34;
    # 你可以在名称（允许 HTML 格式）之后添加其他信息，例如图标
    post = &#34;&#34;
    name = &#34;&#34;
    url = &#34;&#34;
    # 当你将鼠标悬停在此菜单链接上时，将显示的标题
    title = &#34;&#34;
    weight = 1
    #  向菜单项添加用户定义的内容
    [menu.main.params]
      # 添加 CSS 类到菜单项
      class = &#34;&#34;
      # 是否为草稿菜单，类似草稿页面
      draft = false
      #  添加 fontawesome 图标到菜单项
      icon = &#34;&#34;
      #  设置菜单项类型，可选值：[&#34;mobile&#34;, &#34;desktop&#34;]
      type = &#34;&#34;
```

{{&lt; admonition info  &#34;子菜单&#34; true&gt;}} 

考虑到实用性和排版问题，FixIt 主题只支持两层嵌套的菜单，通过在菜单配置中的 `parent` 字段即可。

一个菜单项的父项应该是另一个菜单项的标识符（`identifier`），在菜单中标识符应该是唯一的。

另外，也可以通过配置页面（即 `.md` 文件）的 `front matter` 添加内容到菜单中。 

{{&lt; /admonition &gt;}}

这是一个 `yaml` 示例：

```yaml
---
title: 入门篇
author: Lruihao
menu:
  main:
    title: 探索 Hugo - FixIt 主题的的基础知识和背后的核心概念。
    parent: documentation
    params:
      icon: fa-brands fa-readme
# ...
---
```



### 主题配置

除了 [Hugo 全局配置](https://gohugo.io/overview/configuration/) 和 [菜单配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#menu-configuration) 之外，**FixIt** 主题还允许您在网站配置中定义以下参数。

请打开下面的代码块查看完整的 `config.toml` 示例配置:

```toml
[params]
  #  FixIt 主题版本
  version = &#34;0.2.X&#34; # 例如：&#34;0.2.X&#34;, &#34;0.2.15&#34;, &#34;v0.2.15&#34; 等
  # 网站描述
  description = &#34;这是我的 Hugo FixIt 网站&#34;
  # 网站关键词
  keywords = [&#34;Hugo&#34;, &#34;FixIt&#34;]
  # 网站默认主题样式 [&#34;light&#34;, &#34;dark&#34;, &#34;auto&#34;]
  defaultTheme = &#34;auto&#34;
  # 公共 git 仓库路径，仅在 enableGitInfo 设为 true 时有效
  gitRepo = &#34;&#34;
  #  哪种哈希函数用来 SRI, 为空时表示不使用 SRI
  # [&#34;sha256&#34;, &#34;sha384&#34;, &#34;sha512&#34;, &#34;md5&#34;]
  fingerprint = &#34;&#34;
  #  日期格式
  dateFormat = &#34;2006-01-02&#34;
  # 网站图片，用于 Open Graph 和 Twitter Cards
  images = [&#34;/logo.png&#34;]
  #  开启 PWA 支持
  enablePWA = true
  #  是否自动显示外链图标
  externalIcon = false
  #  默认情况下，FixIt 只会在主页的 HTML 头中注入主题元标记
  # 您可以将其关闭，但如果您不这样做，我们将不胜感激，因为这是观察 FixIt 受欢迎程度上升的好方法
  disableThemeInject = false

  #  应用图标配置
  [params.app]
    # 当添加到 iOS 主屏幕或者 Android 启动器时的标题，覆盖默认标题
    title = &#34;FixIt&#34;
    # 是否隐藏网站图标资源链接
    noFavicon = false
    # 更现代的 SVG 网站图标，可替代旧的 .png 和 .ico 文件
    svgFavicon = &#34;&#34;
    # Safari 图标颜色
    iconColor = &#34;#5bbad5&#34;
    # Windows v8-10 磁贴颜色
    tileColor = &#34;#da532c&#34;
    #  Android 浏览器主题色
    [params.app.themeColor]
      light = &#34;#f8f8f8&#34;
      dark = &#34;#252627&#34;

  #  搜索配置
  [params.search]
    enable = true
    # 搜索引擎的类型 [&#34;lunr&#34;, &#34;algolia&#34;, &#34;fuse&#34;]
    type = &#34;lunr&#34;
    # 文章内容最长索引长度
    contentLength = 4000
    # 搜索框的占位提示语
    placeholder = &#34;&#34;
    #  最大结果数目
    maxResultLength = 10
    #  结果内容片段长度
    snippetLength = 50
    #  搜索结果中高亮部分的 HTML 标签
    highlightTag = &#34;em&#34;
    #  是否在搜索索引中使用基于 baseURL 的绝对路径
    absoluteURL = false
    [params.search.algolia]
      index = &#34;&#34;
      appID = &#34;&#34;
      searchKey = &#34;&#34;
    [params.search.fuse]
      #  https://fusejs.io/api/options.html
      isCaseSensitive = false
      minMatchCharLength = 2
      findAllMatches = false
      location = 0
      threshold = 0.3
      distance = 100
      ignoreLocation = false
      useExtendedSearch = false
      ignoreFieldNorm = false

  # 页面头部导航栏配置
  [params.header]
    #  桌面端导航栏模式 [&#34;sticky&#34;, &#34;normal&#34;, &#34;auto&#34;]
    desktopMode = &#34;sticky&#34;
    #  移动端导航栏模式 [&#34;sticky&#34;, &#34;normal&#34;, &#34;auto&#34;]
    mobileMode = &#34;auto&#34;
    #  页面头部导航栏标题配置
    [params.header.title]
      # LOGO 的 URL
      logo = &#34;/fixit.min.svg&#34;
      # 标题名称
      name = &#34;我的 Hugo FixIt 网站&#34;
      # 你可以在名称（允许 HTML 格式）之前添加其他信息，例如图标
      pre = &#34;&#34;
      # 你可以在名称（允许 HTML 格式）之后添加其他信息，例如图标
      post = &#34;&#34;
      #  是否为标题显示打字机动画
      typeit = false
    #  页面头部导航栏副标题配置
    [params.header.subtitle]
      # 副标题名称
      name = &#34;&#34;
      # 是否为副标题显示打字机动画
      typeit = false

  # 页面底部信息配置
  [params.footer]
    enable = true
    #  自定义内容（支持 HTML 格式）
    # 进阶使用，见参数 `params.customFilePath.footer`
    custom = &#34;&#34;
    #  是否显示 Hugo 和主题信息
    hugo = true
    #  是否显示版权信息
    copyright = true
    #  是否显示作者
    author = true
    # 网站创立年份
    since = 2021
    #  是否显示网站内容总字数
    wordCount = true
    #  公网安备信息，仅在中国使用（支持 HTML 格式）
    gov = &#34;&#34;
    #  ICP 备案信息，仅在中国使用（支持 HTML 格式）
    icp = &#34;&#34;
    # 许可协议信息（支持 HTML 格式）
    license = &#39;&lt;a rel=&#34;license external nofollow noopener noreferrer&#34; href=&#34;https://creativecommons.org/licenses/by-nc/4.0/&#34; target=&#34;_blank&#34;&gt;CC BY-NC 4.0&lt;/a&gt;&#39;
    #  网站创立时间
    [params.footer.siteTime]
      enable = false
      animate = true
      icon = &#34;fa-solid fa-heartbeat&#34;
      pre = &#34;&#34;
      value = &#34;&#34; # e.g. &#34;2021-12-18T16:15:22&#43;08:00&#34;
    #  页面底部行排序，可选值：[&#34;first&#34;, 0, 1, 2, 3, 4, 5, &#34;last&#34;]
    [params.footer.order]
      powered = 0
      copyright = 0
      statistics = 0
      visitor = 0
      beian = 0

  #  Section（所有文章）页面配置
  [params.section]
    # section 页面每页显示文章数量
    paginate = 20
    # 日期格式（月和日）
    dateFormat = &#34;01-02&#34;
    # RSS 文章数目
    rss = 10
    #  最近更新文章设置
    [params.section.recentlyUpdated]
      enable = false
      rss = false
      days = 30
      maxCount = 10

  #  List（目录或标签）页面配置
  [params.list]
    # list 页面每页显示文章数量
    paginate = 20
    # 日期格式（月和日）
    dateFormat = &#34;01-02&#34;
    # RSS 文章数目
    rss = 10

  #  标签云配置
  [params.tagcloud]
    enable = false
    min = 14 # 最小字体大小，单位：px
    max = 32 # 最大字体大小，单位：px
    peakCount = 10 # 每个标签的最大文章数
    orderby = &#34;name&#34; # 标签排序方式，可选值：[&#34;name&#34;, &#34;count&#34;]

  # 主页配置
  [params.home]
    #  RSS 文章数目
    rss = 10
    # 主页个人信息
    [params.home.profile]
      enable = true
      # Gravatar 邮箱，用于优先在主页显示的头像
      gravatarEmail = &#34;&#34;
      # 主页显示头像的 URL
      avatarURL = &#34;/images/avatar.png&#34;
      #  头像菜单链接的 identifier
      avatarMenu = &#34;&#34;
      #  主页显示的网站标题（支持 HTML 格式）
      title = &#34;&#34;
      # 主页显示的网站副标题
      subtitle = &#34;这是我的 Hugo FixIt 网站&#34;
      # 是否为副标题显示打字机动画
      typeit = true
      # 是否显示社交账号
      social = true
      #  免责声明（支持 HTML 格式）
      disclaimer = &#34;&#34;
    # 主页文章列表
    [params.home.posts]
      enable = true
      # 主页每页显示文章数量
      paginate = 6

  #  作者的社交信息设置
  [params.social]
    GitHub = &#34;Lruihao&#34;
    Linkedin = &#34;&#34;
    Twitter = &#34;&#34;
    Instagram = &#34;&#34;
    Facebook = &#34;&#34;
    Telegram = &#34;&#34;
    Medium = &#34;&#34;
    Gitlab = &#34;&#34;
    Youtubelegacy = &#34;&#34;
    Youtubecustom = &#34;&#34;
    Youtubechannel = &#34;&#34;
    Tumblr = &#34;&#34;
    Quora = &#34;&#34;
    Keybase = &#34;&#34;
    Pinterest = &#34;&#34;
    Reddit = &#34;&#34;
    Codepen = &#34;&#34;
    FreeCodeCamp = &#34;&#34;
    Bitbucket = &#34;&#34;
    Stackoverflow = &#34;&#34;
    Weibo = &#34;&#34;
    Odnoklassniki = &#34;&#34;
    VK = &#34;&#34;
    Flickr = &#34;&#34;
    Xing = &#34;&#34;
    Snapchat = &#34;&#34;
    Soundcloud = &#34;&#34;
    Spotify = &#34;&#34;
    Bandcamp = &#34;&#34;
    Paypal = &#34;&#34;
    Fivehundredpx = &#34;&#34;
    Mix = &#34;&#34;
    Goodreads = &#34;&#34;
    Lastfm = &#34;&#34;
    Foursquare = &#34;&#34;
    Hackernews = &#34;&#34;
    Kickstarter = &#34;&#34;
    Patreon = &#34;&#34;
    Steam = &#34;&#34;
    Twitch = &#34;&#34;
    Strava = &#34;&#34;
    Skype = &#34;&#34;
    Whatsapp = &#34;&#34;
    Zhihu = &#34;&#34;
    Douban = &#34;&#34;
    Angellist = &#34;&#34;
    Slidershare = &#34;&#34;
    Jsfiddle = &#34;&#34;
    Deviantart = &#34;&#34;
    Behance = &#34;&#34;
    Dribbble = &#34;&#34;
    Wordpress = &#34;&#34;
    Vine = &#34;&#34;
    Googlescholar = &#34;&#34;
    Researchgate = &#34;&#34;
    Mastodon = &#34;&#34;
    Thingiverse = &#34;&#34;
    Devto = &#34;&#34;
    Gitea = &#34;&#34;
    XMPP = &#34;&#34;
    Matrix = &#34;&#34;
    Bilibili = &#34;&#34;
    ORCID = &#34;&#34;
    Liberapay = &#34;&#34;
    Ko-Fi = &#34;&#34;
    BuyMeaCoffee = &#34;&#34;
    Linktree = &#34;&#34;
    QQ = &#34;&#34;
    QQGroup = &#34;awbwdTtSQ_-H5QGzeJxdWgv6JMbNehNM&#34; # https://qun.qq.com/join.html
    Diaspora = &#34;&#34;
    CSDN = &#34;&#34;
    Discord = &#34;&#34;
    DiscordInvite = &#34;&#34;
    Lichess = &#34;&#34;
    Pleroma = &#34;&#34;
    Kaggle = &#34;&#34;
    MediaWiki= &#34;&#34;
    Plume = &#34;&#34;
    HackTheBox = &#34;&#34;
    RootMe = &#34;&#34;
    Feishu = &#34;&#34;
    TryHackMe = &#34;&#34;
    Phone = &#34;&#34;
    Email = &#34;&#34;
    RSS = true

  #  文章页面配置
  [params.page]
    #  是否启用文章作者头像
    authorAvatar = true
    #  是否在主页隐藏一篇文章
    hiddenFromHomePage = false
    #  是否在搜索结果中隐藏一篇文章
    hiddenFromSearch = false
    #  是否使用 twemoji
    twemoji = false
    # 是否使用 lightgallery
    #  如果设为 &#34;force&#34;，文章中的图片将强制按照画廊形式呈现
    lightgallery = false
    #  是否使用 ruby 扩展语法
    ruby = true
    #  是否使用 fraction 扩展语法
    fraction = true
    #  是否使用 fontawesome 扩展语法
    fontawesome = true
    # 许可协议信息（支持 HTML 格式）
    license = &#39;&lt;a rel=&#34;license external nofollow noopener noreferrer&#34; href=&#34;https://creativecommons.org/licenses/by-nc/4.0/&#34; target=&#34;_blank&#34;&gt;CC BY-NC 4.0&lt;/a&gt;&#39;
    # 是否在文章页面显示原始 Markdown 文档链接
    linkToMarkdown = true
    #  是否在 RSS 中显示全文内容
    rssFullText = false
    #  页面样式 [&#34;narrow&#34;, &#34;normal&#34;, &#34;wide&#34;, ...]
    pageStyle = &#34;normal&#34;
    #   强制使用 Gravatar 作为作者头像
    # gravatarForce = true
    #  开启自动书签支持
    # 如果为 true，则在关闭页面时保存阅读进度
    autoBookmark = false
    #  是否使用 字数统计
    wordCount = true
    #  是否使用 预计阅读
    readingTime = true
    #  文章结束标志
    endFlag = &#34;&#34;
    #  是否开启即时页面
    instantPage = false

    #  转载配置
    [params.page.repost]
      enable = false
      url = &#34;&#34;
    #  目录配置
    [params.page.toc]
      # 是否使用目录
      enable = true
      #  是否保持使用文章前面的静态目录
      keepStatic = false
      # 是否使侧边目录自动折叠展开
      auto = true
      #  目录位置 [&#34;left&#34;, &#34;right&#34;]
      position = &#34;right&#34;
    #  在文章开头显示提示信息，提醒读者文章内容可能过时
    [params.page.expirationReminder]
      enable = false
      # 如果文章最后更新于这天数之前，显示提醒
      reminder = 90
      # 如果文章最后更新于这天数之前，显示警告
      warning = 180
      # 如果文章到期是否关闭评论
      closeComment = false
    #  代码配置
    [params.page.code]
      # 是否显示代码块的复制按钮
      copy = true
      #  是否显示代码块的编辑按钮
      edit = true
      # 默认展开显示的代码行数
      maxShownLines = 10
    #  文章编辑
    [params.page.edit]
      enable = false
      #  编辑的基础链接
      # url = &#34;/edit/branch-name/subdirectory-name&#34; # 相对于 `params.gitRepo`
      # url = &#34;https://github.com/user-name/repo-name/edit/branch-name/subdirectory-name&#34; # 完整链接
      url = &#34;&#34;
    #  KaTeX 数学公式 (https://katex.org)
    [params.page.math]
      enable = true
      # 默认行内定界符是 $ ... $ 和 \( ... \)
      inlineLeftDelimiter = &#34;&#34;
      inlineRightDelimiter = &#34;&#34;
      # 默认块定界符是 $$ ... $$, \[ ... \],  \begin{equation} ... \end{equation} 和一些其它的函数
      blockLeftDelimiter = &#34;&#34;
      blockRightDelimiter = &#34;&#34;
      # KaTeX 插件 copy_tex
      copyTex = true
      # KaTeX 插件 mhchem
      mhchem = true
    #  Mapbox GL JS 配置 (https://docs.mapbox.com/mapbox-gl-js)
    [params.page.mapbox]
      # Mapbox GL JS 的 access token
      accessToken = &#34;&#34;
      # 浅色主题的地图样式
      lightStyle = &#34;mapbox://styles/mapbox/light-v9&#34;
      # 深色主题的地图样式
      darkStyle = &#34;mapbox://styles/mapbox/dark-v9&#34;
      # 是否添加 NavigationControl
      navigation = true
      # 是否添加 GeolocateControl
      geolocate = true
      # 是否添加 ScaleControl
      scale = true
      # 是否添加 FullscreenControl
      fullscreen = true
    #  赞赏设置
    [params.page.reward]
      enable = false
      animation = false
      # 相对于页脚的位置，可选值：[&#34;before&#34;, &#34;after&#34;]
      position = &#34;after&#34;
      # comment = &#34;Buy me a coffee&#34;
      [params.page.reward.ways]
        # wechatpay = &#34;/images/wechatpay.png&#34;
        # alipay = &#34;/images/alipay.png&#34;
        # paypal = &#34;/images/paypal.png&#34;
        # bitcoin = &#34;/images/bitcoin.png&#34;
    #  文章页面的分享信息设置
    [params.page.share]
      enable = true
      Twitter = true
      Facebook = true
      Linkedin = false
      Whatsapp = true
      Pinterest = false
      Tumblr = false
      HackerNews = false
      Reddit = false
      VK = false
      Buffer = false
      Xing = false
      Line = true
      Instapaper = false
      Pocket = false
      Digg = false
      Stumbleupon = false
      Flipboard = false
      Weibo = true
      Renren = false
      Myspace = true
      Blogger = true
      Baidu = false
      Odnoklassniki = false
      Evernote = true
      Skype = false
      Trello = false
      Mix = false
    #  评论系统设置
    [params.page.comment]
      enable = false
      #  Artalk 评论系统设置 (https://artalk.js.org/)
      [params.page.comment.artalk]
        enable = false
        server = &#34;https://yourdomain/api/&#34;
        site = &#34;默认站点&#34;
        placeholder = &#34;&#34;
        noComment = &#34;&#34;
        sendBtn = &#34;&#34;
        editorTravel = true
        flatMode = &#34;auto&#34;
        maxNesting = 3
        #  启用 lightgallery 支持
        lightgallery = false
        locale = &#34;&#34; # 
      #  Disqus 评论系统设置 (https://disqus.com)
      [params.page.comment.disqus]
        enable = false
        # Disqus 的 shortname，用来在文章中启用 Disqus 评论系统
        shortname = &#34;&#34;
      #  Gitalk 评论系统设置 (https://github.com/gitalk/gitalk)
      [params.page.comment.gitalk]
        enable = false
        owner = &#34;&#34;
        repo = &#34;&#34;
        clientId = &#34;&#34;
        clientSecret = &#34;&#34;
      # Valine 评论系统设置 (https://github.com/xCss/Valine)
      [params.page.comment.valine]
        enable = false
        appId = &#34;&#34;
        appKey = &#34;&#34;
        placeholder = &#34;&#34;
        avatar = &#34;mp&#34;
        meta = &#34;&#34;
        requiredFields = &#34;&#34;
        pageSize = 10
        lang = &#34;&#34;
        visitor = true
        recordIP = true
        highlight = true
        enableQQ = false
        serverURLs = &#34;&#34;
        #  emoji 数据文件名称，默认是 &#34;google.yml&#34;
        # [&#34;apple.yml&#34;, &#34;google.yml&#34;, &#34;facebook.yml&#34;, &#34;twitter.yml&#34;]
        # 位于 &#34;themes/FixIt/assets/lib/valine/emoji/&#34; 目录
        # 可以在你的项目下相同路径存放你自己的数据文件：
        # &#34;assets/lib/valine/emoji/&#34;
        emoji = &#34;&#34;
        commentCount = true # 
      #  Waline 评论系统设置 (https://waline.js.org)
      [params.page.comment.waline]
        enable = false
        serverURL = &#34;&#34;
        pageview = false # 
        emoji = [&#34;//unpkg.com/@waline/emojis@1.1.0/weibo&#34;]
        meta = [&#34;nick&#34;, &#34;mail&#34;, &#34;link&#34;]
        requiredMeta = []
        login = &#34;enable&#34;
        wordLimit = 0
        pageSize = 10
        imageUploader = false # 
        highlighter = false # 
        comment = false # 
        texRenderer = false # 
        search = false # 
        recaptchaV3Key = &#34;&#34; # 
        reaction = false # 
      # Facebook 评论系统设置 (https://developers.facebook.com/docs/plugins/comments)
      [params.page.comment.facebook]
        enable = false
        width = &#34;100%&#34;
        numPosts = 10
        appId = &#34;&#34;
        languageCode = &#34;zh_CN&#34;
      #  Telegram Comments 评论系统设置 (https://comments.app)
      [params.page.comment.telegram]
        enable = false
        siteID = &#34;&#34;
        limit = 5
        height = &#34;&#34;
        color = &#34;&#34;
        colorful = true
        dislikes = false
        outlined = false
      #  Commento 评论系统设置 (https://commento.io)
      [params.page.comment.commento]
        enable = false
      #  Utterances 评论系统设置 (https://utteranc.es)
      [params.page.comment.utterances]
        enable = false
        # owner/repo
        repo = &#34;&#34;
        issueTerm = &#34;pathname&#34;
        label = &#34;&#34;
        lightTheme = &#34;github-light&#34;
        darkTheme = &#34;github-dark&#34;
      #  Twikoo 评论系统设置 (https://twikoo.js.org/)
      [params.page.comment.twikoo]
        enable = false
        envId = &#34;&#34;
        region = &#34;&#34;
        path = &#34;&#34;
        visitor = true
        commentCount = true
        #  启用 lightgallery 支持
        lightgallery = false
        #  启用 Katex 支持
        katex = false
      #  Giscus 评论系统设置
      [params.page.comment.giscus]
        enable = false
        repo = &#34;&#34;
        repoId = &#34;&#34;
        category = &#34;&#34;
        categoryId = &#34;&#34;
        mapping = &#34;&#34;
        term = &#34;&#34;
        reactionsEnabled = &#34;1&#34;
        emitMetadata = &#34;0&#34;
        inputPosition = &#34;bottom&#34; # [&#34;top&#34;, &#34;bottom&#34;]
        lightTheme = &#34;light&#34;
        darkTheme = &#34;dark&#34;
        lazyLoad = true
    #  第三方库配置
    [params.page.library]
      [params.page.library.css]
        # someCSS = &#34;some.css&#34;
        # 位于 &#34;assets/&#34;
        # 或者
        # someCSS = &#34;https://cdn.example.com/some.css&#34;
      [params.page.library.js]
        # someJavascript = &#34;some.js&#34;
        # 位于 &#34;assets/&#34;
        # 或者
        # someJavascript = &#34;https://cdn.example.com/some.js&#34;
    #  页面 SEO 配置
    [params.page.seo]
      # 图片 URL
      images = []
      # 出版者信息
      [params.page.seo.publisher]
        name = &#34;&#34;
        logoUrl = &#34;&#34;

  #  TypeIt 配置
  [params.typeit]
    # 每一步的打字速度（单位是毫秒）
    speed = 100
    # 光标的闪烁速度（单位是毫秒）
    cursorSpeed = 1000
    # 光标的字符（支持 HTML 格式）
    cursorChar = &#34;|&#34;
    # 打字结束之后光标的持续时间（单位是毫秒，&#34;-1&#34; 代表无限大）
    duration = -1
    #  打字完成后是否会连续循环
    loop = false

  #  Mermaid 配置
  [params.mermaid]
    # 取值详见 https://mermaid-js.github.io/mermaid/#/Setup?id=theme
    themes = [&#34;neutral&#34;, &#34;dark&#34;]

  #  盘古之白配置
  [params.pangu]
    # 适用于中文写作用户
    enable = false
    selector = &#34;article&#34; # 

  #  水印配置
  # 详细参数见 https://github.com/Lruihao/watermark#readme
  [params.watermark]
    enable = false
    # 水印内容（允许 HTML 格式）
    content = &#34;&#34;
    # 水印透明度
    opacity = 0.1
    # 水印父节点
    appendTo = &#34;.wrapper&gt;main&#34;
    # 单水印宽度 单位：px
    width = 150
    # 单水印高度 单位：px
    height = 20
    # 水印行间距 单位：px
    rowSpacing = 60
    # 水印列间距 单位：px
    colSpacing = 30
    # 水印旋转角度 单位：deg
    rotate = 15
    # 水印字体大小，单位：rem
    fontSize = 0.85
    #  水印字体
    fontFamily = &#34;inherit&#34;

  #  不蒜子统计
  [params.ibruce]
    enable = true
    # 在文章中开启
    enablePost = false

  # 网站验证代码，用于 Google/Bing/Yandex/Pinterest/Baidu/360/Sogou
  [params.verification]
    google = &#34;&#34;
    bing = &#34;&#34;
    yandex = &#34;&#34;
    pinterest = &#34;&#34;
    baidu = &#34;&#34;
    so = &#34;&#34;
    sogou = &#34;&#34;

  #  网站 SEO 配置
  [params.seo]
    # 图片 URL
    image = &#34;&#34;
    # 缩略图 URL
    thumbnailUrl = &#34;&#34;

  #  网站分析配置
  [params.analytics]
    enable = false
    # Google Analytics
    [params.analytics.google]
      id = &#34;&#34;
      # 是否匿名化用户 IP
      anonymizeIP = true
    # Fathom Analytics
    [params.analytics.fathom]
      id = &#34;&#34;
      # 自行托管追踪器时的主机路径
      server = &#34;&#34;

  #  Cookie 许可配置
  [params.cookieconsent]
    enable = true
    # 用于 Cookie 许可横幅的文本字符串
    [params.cookieconsent.content]
      message = &#34;&#34;
      dismiss = &#34;&#34;
      link = &#34;&#34;

  #  第三方库文件的 CDN 设置
  [params.cdn]
    # CDN 数据文件名称，默认不启用 [&#34;jsdelivr.yml&#34;, &#34;unpkg.yml&#34;, ...]
    # 位于 &#34;themes/FixIt/assets/data/cdn/&#34; 目录
    # 可以在你的项目下相同路径存放你自己的数据文件：&#34;assets/data/cdn/&#34;
    # data = &#34;unpkg.yml&#34;

  #  兼容性设置
  [params.compatibility]
    # 是否使用 Polyfill.io 来兼容旧式浏览器
    polyfill = false
    # 是否使用 object-fit-images 来兼容旧式浏览器
    objectFit = false

  #  在左上角或者右上角显示 GitHub 开源链接
  [params.githubCorner]
    enable = false
    permalink = &#34;https://github.com/hugo-fixit/FixIt&#34;
    title = &#34;在 GitHub 上查看源代码&#34;
    position = &#34;right&#34; # [&#34;left&#34;, &#34;right&#34;]

  #  Gravatar 设置
  [params.gravatar]
    #  取决于作者邮箱，作者邮箱未设置则使用本地头像
    enable = false
    # Gravatar 主机，默认：“www.gravatar.com”
    host = &#34;www.gravatar.com&#34; # [&#34;cn.gravatar.com&#34;, &#34;gravatar.loli.net&#34;, ...]
    style = &#34;&#34; # [&#34;&#34;, &#34;mp&#34;, &#34;identicon&#34;, &#34;monsterid&#34;, &#34;wavatar&#34;, &#34;retro&#34;, &#34;blank&#34;, &#34;robohash&#34;]

  #  返回顶部
  [params.backToTop]
    enable = true
    # 在 b2t 按钮中显示滚动百分比
    scrollpercent = false

  #  阅读进度条
  [params.readingProgress]
    enable = false
    # 可用值：[&#34;left&#34;, &#34;right&#34;]
    start = &#34;left&#34;
    # 可用值：[&#34;top&#34;, &#34;bottom&#34;]
    position = &#34;top&#34;
    reversed = false
    light = &#34;&#34;
    dark = &#34;&#34;
    height = &#34;2px&#34;

  #  页面加载期间顶部的进度条
  # 有关详细信息：https://github.com/CodeByZach/pace
  [params.pace]
    enable = false
    # 所有可用颜色：
    # [&#34;black&#34;, &#34;blue&#34;, &#34;green&#34;, &#34;orange&#34;, &#34;pink&#34;, &#34;purple&#34;, &#34;red&#34;, &#34;silver&#34;, &#34;white&#34;, &#34;yellow&#34;]
    color = &#34;blue&#34;
    # 所有可用主题：
    # [&#34;barber-shop&#34;, &#34;big-counter&#34;, &#34;bounce&#34;, &#34;center-atom&#34;, &#34;center-circle&#34;, &#34;center-radar&#34;, &#34;center-simple&#34;,
    # &#34;corner-indicator&#34;, &#34;fill-left&#34;, &#34;flash&#34;, &#34;flat-top&#34;, &#34;loading-bar&#34;, &#34;mac-osx&#34;, &#34;material&#34;, &#34;minimal&#34;]
    theme = &#34;minimal&#34;

  #  定义自定义文件路径
  # 在站点目录 `layouts/partials/custom` 中创建您的自定义文件，并取消注释下面需要的文件
  [params.customFilePath]
    # aside = &#34;custom/aside.html&#34;
    # profile = &#34;custom/profile.html&#34;
    # footer = &#34;custom/footer.html&#34;

  #  开发者选项
  [params.dev]
    enable = false
    # 检查更新
    c4u = false
    # 请勿公开展示！
    githubToken = &#34;&#34;
    # 移动端开发者工具配置
    [params.dev.mDevtools]
      enable = false
      # 支持 &#34;vConsole&#34;, &#34;eruda&#34;
      type = &#34;vConsole&#34;

# Hugo 解析文档的配置
[markup]
  # 语法高亮设置 (https://gohugo.io/content-management/syntax-highlighting)
  [markup.highlight]
    ################## 必要的配置 ##################
    # https://github.com/hugo-fixit/FixIt/issues/43
    codeFences = true
    lineNos = true
    lineNumbersInTable = true
    noClasses = false
    ################## 必要的配置 ##################
    guessSyntax = true
  # Goldmark 是 Hugo 0.60 以来的默认 Markdown 解析库
  [markup.goldmark]
    [markup.goldmark.extensions]
      definitionList = true
      footnote = true
      linkify = true
      strikethrough = true
      table = true
      taskList = true
      typographer = true
    [markup.goldmark.renderer]
      # 是否在文档中直接使用 HTML 标签
      unsafe = true
  # 目录设置
  [markup.tableOfContents]
    startLevel = 2
    endLevel = 6

# 作者配置
[author]
  name = &#34;xxxx&#34;
  email = &#34;&#34;
  link = &#34;&#34;
  avatar = &#34;/images/avatar.png&#34; # 

# 网站地图配置
[sitemap]
  changefreq = &#34;weekly&#34;
  filename = &#34;sitemap.xml&#34;
  priority = 0.5

# Permalinks 配置 (https://gohugo.io/content-management/urls#permalinks)
[Permalinks]
  # posts = &#34;:year/:month/:filename&#34;
  posts = &#34;:filename&#34;

# 隐私信息配置 (https://gohugo.io/about/hugo-and-gdpr/)
[privacy]
  [privacy.twitter]
    enableDNT = true
  [privacy.youtube]
    privacyEnhanced = true

# 
[mediaTypes]
  # 用于输出 Markdown 格式文档的设置
  [mediaTypes.&#34;text/markdown&#34;]
    suffixes = [&#34;md&#34;]
  # 用于输出 txt 格式文档的设置
  [mediaTypes.&#34;text/plain&#34;]
    suffixes = [&#34;txt&#34;]

# 
[outputFormats]
  # 用于输出 Markdown 格式文档的设置
  [outputFormats.MarkDown]
    mediaType = &#34;text/markdown&#34;
    isPlainText = true
    isHTML = false
  #  用于输出 baidu_urls.txt 文件的设置
  [outputFormats.BaiduUrls]
    baseName = &#34;baidu_urls&#34;
    mediaType = &#34;text/plain&#34;
    isPlainText = true
    isHTML = false

#  用于 Hugo 输出文档的设置
[outputs]
  home = [&#34;HTML&#34;, &#34;RSS&#34;, &#34;JSON&#34;, &#34;BaiduUrls&#34;]
  page = [&#34;HTML&#34;, &#34;MarkDown&#34;]
  section = [&#34;HTML&#34;, &#34;RSS&#34;]
  taxonomy = [&#34;HTML&#34;, &#34;RSS&#34;]
  taxonomyTerm = [&#34;HTML&#34;]
```

[![完整配置下的预览](https://fixit.lruihao.cn/zh-cn/documentation/basics/full-configuration-preview.zh-cn.png)](https://fixit.lruihao.cn/zh-cn/documentation/basics/full-configuration-preview.zh-cn.png)																			完整配置下的预览



#### CDN 配置

```toml
[params.cdn]
  # CDN 数据文件名称，默认不启用 [&#34;jsdelivr.yml&#34;, &#34;unpkg.yml&#34;, ...]
  data = &#34;&#34;
```

默认的 CDN 数据文件位于 `themes/FixIt/assets/data/cdn/` 目录。 可以在你的项目下相同路径存放你自己的数据文件：`assets/data/cdn/`。

#### 社交链接配置

你可以直接配置你的社交 ID 来生成一个默认社交链接和图标：

```toml
[params.social]
  Mastodon = &#34;@xxxx&#34;
```

生成的社交链接是 `https://mastodon.technology/@xxxx`。

或者你可以通过一个字典来设置更多的选项：

```toml
[params.social]
  [params.social.Mastodon]
    # 排列图标时的权重（权重越大，图标的位置越靠后）
    weight = 0
    # 你的社交 ID
    id = &#34;@xxxx&#34;
    # 你的社交链接的前缀
    prefix = &#34;https://mastodon.social/&#34;
    # 当鼠标停留在图标上时的提示内容
    title = &#34;Mastodon&#34;
```

所有支持的社交链接的默认数据位于 `themes/FixIt/assets/data/social.yaml`。 你可以参考它来配置你的社交链接。

#### 搜索配置

基于 [Lunr.js](https://lunrjs.com/)、 [algolia](https://www.algolia.com/) 或 [Fuse.js](https://fusejs.io/)，**FixIt** 主题支持搜索功能，详见 [主题配置](https://fixit.lruihao.cn/zh-cn/documentation/basics/#theme-configuration) 的 `params.search` 配置。

为了生成搜索功能所需要的 `index.json`, 请在你的站点配置中添加 `JSON` 输出文件类型到 `outputs` 部分的 `home` 字段中。

```toml
[outputs]
  home = [&#34;HTML&#34;, &#34;RSS&#34;, &#34;JSON&#34;]
```

{{&lt; admonition info &#34;**关于 algolia 的使用技巧**&#34; true&gt;}} 

你需要上传 `index.json` 到 algolia 来激活搜索功能。你可以使用浏览器来上传 `index.json` 文件但是一个自动化的脚本可能效果更好。 [Algolia Atomic](https://github.com/chrisdmacrae/atomic-algolia) 是一个不错的选择。 为了兼容 Hugo 的多语言模式，你需要上传不同语言的 `index.json` 文件到对应的 algolia index, 例如 `zh-cn/index.json` 或 `fr/index.json`……

 {{&lt; /admonition &gt;}}

### 网站图标，浏览器配置，网站清单

强烈建议你把：

- apple-touch-icon.png (180x180)
- favicon-32x32.png (32x32)
- favicon-16x16.png (16x16)
- mstile-150x150.png (150x150)
- android-chrome-192x192.png (192x192)
- android-chrome-512x512.png (512x512)

放在 `/static` 目录。利用 https://realfavicongenerator.net/ 可以很容易地生成这些文件。

可以自定义 `browserconfig.xml` 和 `site.webmanifest` 文件来设置 `theme-color` 和 `background-color`。

### 多语言和 i18n

**FixIt** 主题完全兼容 Hugo 的多语言模式，并且支持在网页上切换语言。

![语言切换](https://fixit.lruihao.cn/zh-cn/documentation/basics/language-switch.gif)

​																					语言切换

#### 兼容性

[![FixIt 0.2.10 | 更改](https://fixit.lruihao.cn/svg/version/0.2.10-changed.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.10)

| 语言         | Hugo 代码 | HTML `lang` 属性 | 主题文档 | Lunr.js 支持 |
| :----------- | :-------: | :--------------: | :------: | :----------: |
| 英语         |   `en`    |       `en`       |          |              |
| 简体中文     |  `zh-cn`  |     `zh-CN`      |          |              |
| 繁体中文     |  `zh-tw`  |     `zh-TW`      |          |              |
| 法语         |   `fr`    |       `fr`       |          |              |
| 波兰语       |   `pl`    |       `pl`       |          |              |
| 巴西葡萄牙语 |  `pt-br`  |     `pt-BR`      |          |              |
| 意大利语     |   `it`    |       `it`       |          |              |
| 西班牙语     |   `es`    |       `es`       |          |              |
| 德语         |   `de`    |       `de`       |          |              |
| 塞尔维亚语   |   `sr`    |       `sr`       |          |              |
| 俄语         |   `ru`    |       `ru`       |          |              |
| 罗马尼亚语   |   `ro`    |       `ro`       |          |              |
| 越南语       |   `vi`    |       `vi`       |          |              |

#### 基本配置

学习了 [Hugo 如何处理多语言网站](https://gohugo.io/content-management/multilingual) 之后，请在站点配置中定义你的网站语言。

例如，一个支持英语，中文和法语的网站配置：

然后，对于每个新页面，将语言代码附加到文件名中。

单个文件 `my-page.md` 需要分为三个文件：

- 英语：`my-page.en.md`
- 中文：`my-page.zh-cn.md`
- 法语：`my-page.fr.md`

{{&lt; admonition info &#34;技巧&#34; true&gt;}} 也可以使用 [文章前置参数](https://gohugo.io/content-management/multilingual#translate-your-content) 来翻译网址。 {{&lt; /admonition &gt;}}

#### 修改默认的翻译字符串

翻译字符串用于在主题中使用的常见默认值。 目前提供 [一些语言](https://fixit.lruihao.cn/zh-cn/documentation/basics/#language-compatibility) 的翻译，但你可能自定义其他语言或覆盖默认值。

要覆盖默认值，请在你项目的 i18n 目录 `i18n/&lt;languageCode&gt;.toml` 中创建一个新文件，并从 `themes/FixIt/i18n/en.toml` 中获得提示。

另外，由于你的翻译可能会帮助到其他人，请花点时间通过 [创建一个 PR ](https://github.com/hugo-fixit/FixIt/pulls) 来贡献主题翻译，谢谢！


---

> 作者:   
> URL: https://blog.funvip.live/tutorial/shili-rumenpian/  
> 转载 URL: https://fixit.lruihao.cn/zh-cn/documentation/basics/
