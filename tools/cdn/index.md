# 🛬CDN资源库


> CDN公共库是指将常用的JS库存放在CDN节点，以方便广大开发者直接调用。

<!--more-->

> 与将JS库存放在服务器单机上相比，CDN公共库更加稳定、高速。现在web应用都在使用JS类库，这些类库小的几十K，大的几百K，而国内网络访问速度大家都知道不是那么惬意，所以给各位开发者推荐常用JS类库的CDN缓存，这样不管客户在哪里访问你的页面，调用公共类库的速度都会为你的页面节省很多时间。
>
> 一般的CDN公共库都会包含全球所有最流行的开源JavaScript库，你可以在自己的网页上直接通过script标记引用这些资源。这样做不仅可以为您 节省流量，还能通过CDN加速，获得更快的访问速度。

### 日常推荐

|      | 域名                                                      | 状态     |
| :--- | :-------------------------------------------------------- | -------- |
| √    | [https://cdn.bytedance.com](https://cdn.bytedance.com/)   | **可用** |
| √    | [https://www.staticfile.org](https://www.staticfile.org/) | **可用** |
| √    | [https://lib.sinaapp.com](https://lib.sinaapp.com/)       | **可用** |
| √    | [http://jscdn.upai.com](http://jscdn.upai.com/)           | **可用** |
| √    | [https://cdn.baomitu.com](https://cdn.baomitu.com/)       | **可用** |
| √    | [https://www.bootcdn.cn](https://www.bootcdn.cn/)         | **可用** |
| √    | [https://cdnjs.com](https://cdnjs.com/)                   | **可用** |
| √    | [https://unpkg.com](https://unpkg.com/)                   | **可用** |
| √    | [http://www.jsdelivr.com](https://www.jsdelivr.com/)      | **可用** |
| √    | https://docs.microsoft.com/en-us/aspnet/ajax/cdn          | **可用** |

### JSDelivrs

**jsdelivr - github/npm CDN国内加速节点**

> JSDelivrs是由@Cloudflare提供的免费开源公共CDN。  
> 默认的提供的节点是：`cdn.jsdelivr.net` 该节点国内几乎不可用，需要使用可用性高的节点作为替代。

👉jsdelivr节点：常用于加速GitHub/npm项目，可通过更改节点改善项目在国内的可用性。

<table><tbody><tr><td>节点服务器</td><td>提供商</td><td>可用性</td></tr><tr><td>gcore.jsdelivr.net</td><td>Gcore节点</td><td>高</td></tr><tr><td>testingcf.jsdelivr.net</td><td>Cloudflare节点</td><td>高</td></tr><tr><td>quantil.jsdelivr.net</td><td>Quantil节点</td><td>尚可</td></tr><tr><td>fastly.jsdelivr.net</td><td>Fastly节点</td><td>尚可</td></tr><tr><td>originfastly.jsdelivr.net</td><td>Fastly节点</td><td>低</td></tr><tr><td>test1.jsdelivr.net</td><td>Cloudflare节点</td><td>低</td></tr><tr><td>cdn.jsdelivr.net</td><td>通用节点</td><td>低</td></tr></tbody></table>

👉个人提供的jsdelivr节点

<table><tbody><tr><td>节点服务器</td><td>提供商</td><td>使用须知</td></tr><tr><td>jsd.onmicrosoft.cn</td><td>国内CDN</td><td>仅可自用，不可滥用</td></tr><tr><td>jsdelivr.b-cdn.net</td><td>台湾CDN</td><td>速度快，稳定性未知</td></tr></tbody></table>

👉npm节点：unpkg.com国内几乎不可用，可用下方国内cdn节点，公益节点仅可自用，不可滥用。

<table><tbody><tr><td>npm.elemecdn.com</td><td>饿了么</td><td>同步快</td></tr><tr><td>npm.onmicrosoft.cn</td><td>公益</td><td>需准确的版本号</td></tr><tr><td>unpkg.zhimg.com</td><td>知乎</td><td>同步慢</td></tr><tr><td>npm.akass.cn</td><td>公益</td><td>需准确的版本号</td></tr><tr><td>cdn.chuqis.com/npm/</td><td>公益</td><td>需准确的版本号</td></tr><tr><td>code.bdstatic.com/npm</td><td>百度</td><td>仅同步热门包</td></tr></tbody></table>

### **节点搜索服务**

⭐️  资源描述：CDNJSCN 是一项免费开源 CDN (国内)搜索服务，提供 CDNJS 库的搜索，加速链接转换服务，此外还提供 Github 、UNPKG 、Google 前端公共库、Google Fonts加速链接的替换

🌐资源地址：[点击跳转](https://cdnjs.shssedu.ac.cn/)



---

> 作者: [聪](/about)  
> URL: https://blog.funvip.live/tools/cdn/  

