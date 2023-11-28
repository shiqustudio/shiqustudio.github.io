# ⬇️下载工具


> 资源下载工具汇总

<!--more-->

### Motrix

![Motrix下载器](https://i.loli.net/2021/10/27/t1g8hNGUnf4BwVQ.png "Motrix下载器")

⭐️  资源描述：Motrix是一款基于Aria2的免费开源下载管理工具，支持几乎所有下载方式，支持Windows、Mac、Linux主流操作系统。

> Motrix可以自动同步热门的Tracker，对于经常下载[种籽+词粒资源](/posts/搜索引擎/)堪称神器。且在批量下载上稳定性不错。**下载速度取决于资源本身的热度，如资源热度较低，下载不动属于很正常的情况，可以尝试更换热度较高的资源。**

🌐 资源地址：🔽[官网下载](https://motrix.app/zh-CN/download) | ❓ [常见问题解决](https://www.yuque.com/moapp/help/issues)

### FDM

⭐️  资源描述：Free Download Manager（简称FDM）是一款支持Windows/安卓/Mac的免费下载工具，相较于IDM和NDM的简陋洁面，FDM的UI比较舒服，同样支持多线程下载。**下载文件的速度往往取决于自身的网络环境，及文件服务器速度，与下载软件关系不大。**

✅桌面端有提供[.crx浏览器扩展](/tools/浏览器工具/)，装完后可接管Edge、Chrome浏览器下载操作。

🌐 资源地址：🔽[官网下载](https://www.freedownloadmanager.org/) | 🔽[123网盘下载](https://www.123pan.com/s/V65A-OXlLd.html) | 👉[火狐浏览器扩展](https://addons.mozilla.org/firefox/addon/free-download-manager-addon/) |👉[谷歌浏览器扩展](https://chrome.google.com/webstore/detail/free-download-manager-chr/ahmpjcflkgiildlgicmcieglgoilbfdp/)`国内无法访问可以通过上方下载链接下载.crx安装`

### NDM

⭐️  资源描述：ndm（NeatDownloadManager） 是一款与idm 无论是界面还是功能都极度相似的下载软件，支持32线程。与idm最大的区别是 ndm是一款完全免费的下载工具，且支持Mac系统。嗅探方便稍逊idm一筹，下载方面没区别。

✅安装[ndm谷歌浏览器扩展](https://chrome.crxsoso.com/webstore/detail/cpcifbdmkopohnnofedkjghjiclmhdah)、[ndm火狐浏览器扩展](https://addons.mozilla.org/en-US/firefox/addon/neatdownloadmanager-extension/)后即可接管浏览器及嗅探功能。

🌐 资源地址：🔽[官网下载](https://www.neatdownloadmanager.com/) | 🔽[123网盘下载](https://www.123pan.com/s/V65A-DXlLd.html)

### BitTorrent Tracker

> 公共 **BitTorrent Tracker** 部分内容来源：[TrackersList官网](https://trackerslist.com/#/zh) 由Github：[XIU2](https://github.com/XIU2/)维护。

#### Best Tracker

🌐 资源地址：[点击查看](https://trackerslist.com/best.txt)

#### Aria2 Tracker

```auto
https://trackerslist.com/all_aria2.txt
```

#### BitTorrent Tracker

```auto
https://trackerslist.com/all.txt
```

> 其他自动更新列表

🧩[开源地址](http://github.itzmx.com/1265578519/OpenTracker/master/tracker.txt)  | 🧩[开源地址](https://raw.githubusercontent.com/ngosang/trackerslist/master/trackers_all.txt)

BitTorrent Tracker列表可根据自己体验情况选择使用哪个列表，上面的列表都是每天更新，在这里感谢这些默默维护列表的大佬们。

#### 如何使用？

**BitComet (比特彗星)** - 比特彗星便携版(已配置 Tracker)：👉[点击查看](https://lanzoup.com/b073c7g4f)

![请输入图片描述](https://i2.wp.com/tvax4.sinaimg.cn/large/6f8a2832gy1ga5tp502d8j20tl0bfwer.jpg "请输入图片描述")

**工具 - 选项 - Tracker**

✅ 勾选两个选项 并在最下方输入框填写 Tracker URL，然后点击 \[立即更新\] 按钮后，上面的大输入框就会显示获取的 Tracker 了。

![请输入图片描述](https://i2.wp.com/tvax4.sinaimg.cn/large/6f8a2832gy1ga5tpdj0kvj20n00jkt9a.jpg "请输入图片描述")

✅ **qBittorrent Enhanced Edition (增强版)**  
![请输入图片描述](https://i2.wp.com/tvax4.sinaimg.cn/large/6f8a2832gy1ga5tpliv3nj20qi05zjrb.jpg "请输入图片描述")  🧩Github：[点击跳转](https://github.com/c0re100/qBittorrent-Enhanced-Edition)

> 基于 qBittorrent 制作，增加了很多功能，例如 订阅 Tracker URL 功能，可以很方便的配合本项目使用。
>
> 选项\[齿轮图标\] - BitTorrent 并填写 Tracker URL 后点击 \[Apply\] 保存，然后重启 qBittorrentEE 。

![请输入图片描述](https://i2.wp.com/tvax4.sinaimg.cn/large/6f8a2832gy1ga5tpqk0bij20q80lp0t5.jpg "请输入图片描述")**Aria2**

复制 Aria2 格式的 Tracker 文件中内容后，粘贴到 `aria2.conf` 配置文件中的 `bt-tracker=` 后面

```auto
bt-tracker=http://xxx.xx:80/announce,udp://yyy.yy:80/announce
```

注意： 粘贴前请先删除旧的资源Tracker 内容，避免格式错误！

#### ⁉️Tracker 连不上？

这是正常现象。目前网上热门的 Tracker 大都是国外服务器。

+   一方面 是一些国外 Tracker 服务器国内链接质量不行（丢包、速度慢、干扰等）。  
    （我发现 HTTPS 的链接成功率更高，HTTP这种明文的 以及 UDP 这种经常被运营商干扰、限制的就很蛋疼了）
+   一方面 是一些国外 Tracker 服务器屏蔽了国内连接（迅雷丢人丢到国外了）。
+   一方面 是这些国外 Tracker 服务器没有你下载的资源信息。

况且 Tracker 数量多少不会影响 BT 软件运行的（都是多线程连接），所以也不需要在意这些连不上的，软件重试几次连不上就忽略了。

#### ⁉️下载速度慢？

BT 下载速度取决于 其他下载同一资源的用户上传速度。

也就是做种的人越多（做种就是上传文件给他人），你的下载速度越快！如果一个资源没人提供上传，你就会完全没有下载速度。

做种： 指上传文件数据给其他 BT 用户的行为。

Tracker 的作用就是更快的找到其他下载同一资源的用户，并帮助你们之间建立链接，间接提高 BT 下载速度（前提是有人做种）。

不仅仅要关注用户数量，还有用户质量，国内绝大部分人都没有公网IP，所以上传速度捉急\[没有公网IP仅影响上传速度，几乎不影响下载速度\]，另一方面也是奸商运营商上传不对等，除此之外还老是限制/干扰 BT，这也是为什么国内BT环境这么差的主要原因。

#### 🟢Tracker来源

该项目汇集了以下公共跟踪器列表：

[https://github.com/ngosang/trackerslist](https://github.com/ngosang/trackerslist)  
[https://newtrackon.com/list](https://newtrackon.com/list)  
[https://torrents.io/tracker-list/](https://torrents.io/tracker-list/)  
[http://github.itzmx.com/1265578519/OpenTracker/master/tracker.txt](http://github.itzmx.com/1265578519/OpenTracker/master/tracker.txt)  
[https://tinytorrent.net/best-torrent-tracker-list-updated/](https://tinytorrent.net/best-torrent-tracker-list-updated/)  
[https://torrenttrackerss.com/torrent-tracker-list/](https://torrenttrackerss.com/torrent-tracker-list/)  
[http://www.torrenttrackerlist.com/torrent-tracker-list](http://www.torrenttrackerlist.com/torrent-tracker-list)


---

> 作者: [聪](/about)  
> URL: https://blog.funvip.live/tools/%E4%B8%8B%E8%BD%BD%E5%B7%A5%E5%85%B7/  

