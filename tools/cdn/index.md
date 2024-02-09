# 🛬CDN资源库


💡 CDN公共库是指将常用的JS库存放在CDN节点，以方便广大开发者直接调用。

&lt;!--more--&gt;

&gt; 与将JS库存放在服务器单机上相比，CDN公共库更加稳定、高速。现在web应用都在使用JS类库，这些类库小的几十K，大的几百K，而国内网络访问速度大家都知道不是那么惬意，所以给各位开发者推荐常用JS类库的CDN缓存，这样不管客户在哪里访问你的页面，调用公共类库的速度都会为你的页面节省很多时间。
&gt;
&gt; 一般的CDN公共库都会包含全球所有最流行的开源JavaScript库，你可以在自己的网页上直接通过script标记引用这些资源。这样做不仅可以为您 节省流量，还能通过CDN加速，获得更快的访问速度。

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

&gt; JSDelivrs是由@Cloudflare提供的免费开源公共CDN。  
&gt; 默认的提供的节点是：`cdn.jsdelivr.net` 该节点国内几乎不可用，需要使用可用性高的节点作为替代。

👉jsdelivr节点：常用于加速GitHub/npm项目，可通过更改节点改善项目在国内的可用性。

&lt;table&gt;&lt;tbody&gt;&lt;tr&gt;&lt;td&gt;节点服务器&lt;/td&gt;&lt;td&gt;提供商&lt;/td&gt;&lt;td&gt;可用性&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;gcore.jsdelivr.net&lt;/td&gt;&lt;td&gt;Gcore节点&lt;/td&gt;&lt;td&gt;高&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;testingcf.jsdelivr.net&lt;/td&gt;&lt;td&gt;Cloudflare节点&lt;/td&gt;&lt;td&gt;高&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;quantil.jsdelivr.net&lt;/td&gt;&lt;td&gt;Quantil节点&lt;/td&gt;&lt;td&gt;尚可&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;fastly.jsdelivr.net&lt;/td&gt;&lt;td&gt;Fastly节点&lt;/td&gt;&lt;td&gt;尚可&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;originfastly.jsdelivr.net&lt;/td&gt;&lt;td&gt;Fastly节点&lt;/td&gt;&lt;td&gt;低&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;test1.jsdelivr.net&lt;/td&gt;&lt;td&gt;Cloudflare节点&lt;/td&gt;&lt;td&gt;低&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;cdn.jsdelivr.net&lt;/td&gt;&lt;td&gt;通用节点&lt;/td&gt;&lt;td&gt;低&lt;/td&gt;&lt;/tr&gt;&lt;/tbody&gt;&lt;/table&gt;

👉个人提供的jsdelivr节点

&lt;table&gt;&lt;tbody&gt;&lt;tr&gt;&lt;td&gt;节点服务器&lt;/td&gt;&lt;td&gt;提供商&lt;/td&gt;&lt;td&gt;使用须知&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;jsd.onmicrosoft.cn&lt;/td&gt;&lt;td&gt;国内CDN&lt;/td&gt;&lt;td&gt;仅可自用，不可滥用&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;jsdelivr.b-cdn.net&lt;/td&gt;&lt;td&gt;台湾CDN&lt;/td&gt;&lt;td&gt;速度快，稳定性未知&lt;/td&gt;&lt;/tr&gt;&lt;/tbody&gt;&lt;/table&gt;

👉npm节点：unpkg.com国内几乎不可用，可用下方国内cdn节点，公益节点仅可自用，不可滥用。

&lt;table&gt;&lt;tbody&gt;&lt;tr&gt;&lt;td&gt;npm.elemecdn.com&lt;/td&gt;&lt;td&gt;饿了么&lt;/td&gt;&lt;td&gt;同步快&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;npm.onmicrosoft.cn&lt;/td&gt;&lt;td&gt;公益&lt;/td&gt;&lt;td&gt;需准确的版本号&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;unpkg.zhimg.com&lt;/td&gt;&lt;td&gt;知乎&lt;/td&gt;&lt;td&gt;同步慢&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;npm.akass.cn&lt;/td&gt;&lt;td&gt;公益&lt;/td&gt;&lt;td&gt;需准确的版本号&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;cdn.chuqis.com/npm/&lt;/td&gt;&lt;td&gt;公益&lt;/td&gt;&lt;td&gt;需准确的版本号&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;code.bdstatic.com/npm&lt;/td&gt;&lt;td&gt;百度&lt;/td&gt;&lt;td&gt;仅同步热门包&lt;/td&gt;&lt;/tr&gt;&lt;/tbody&gt;&lt;/table&gt;

### **节点搜索服务**

⭐️  资源描述：CDNJSCN 是一项免费开源 CDN (国内)搜索服务，提供 CDNJS 库的搜索，加速链接转换服务，此外还提供 Github 、UNPKG 、Google 前端公共库、Google Fonts加速链接的替换

🌐资源地址：[点击跳转](https://cdnjs.shssedu.ac.cn/)



---

> 作者:   
> URL: https://blog.funvip.live/tools/cdn/  

