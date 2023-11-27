# ⛓️防盗链


网络中收集的一些**图片镜像缓存服务**，在很多时候可以起到不错的用途。

```auto
https://i3.wp.com/  
```

还可以更改为`i1.wp.com` `i2.wp.com` Wordpress提供的图像缓存服务，需要去掉http/https协议

```auto
https://cdn.cdnjson.com/
```

cdnjson提供的图像缓存服务，可以加速新浪微博/知乎等开启防盗链的图片，需要去掉http/https协议

```auto
https://img.noobzone.ru/getimg.php?url=
```

俄罗斯的图片缓存服务，支持大部分的图片链接，可以加http/https协议，不加也能识别。

```auto
https://cors.zme.ink/
```

基于Cloudflare Workers搭建的跨域代理缓存服务，可以缓存所有内容，可加http/https协议，不加也行。

> 图像缓存可以用来做什么？

+   可以将有防盗链的图片引用到网页，并成功显示。
+   可以将http图片引用到https页面而不出现证书问题。
+   可以将xxx的图片，成功加载。
+   可以将比较慢的图片资源，加快显示。

目前新浪图床有一个没有做防盗链的外链域名：图片链接 `/large/xxxx.jpg` 前的链接修改为 `gzw.sinaimg.cn` 

>如链接
>
>https://**tvax4**.sinaimg.cn/large/6f8a2832ly1gjqiig3g6uj22nh1ahto0.jpg
>
>由于新浪微博做了防盗链，无论是直接引用网站或直接在浏览器中打开都会显示403错误。
>
>修改为
>
>https://**gzw**.sinaimg.cn/large/6f8a2832ly1gjqiig3g6uj22nh1ahto0.jpg
>
>这样就可以打开，这种方式是直接使用的新浪微博服务器，速度快，缺点是不知道啥时候又会做防盗链。
>
>更稳定的方式是直接在链接前加上图片加速服务，需要去掉图片链接的**https://** 这种方式的缺点是国内速度不如直接使用新浪微博的服务器。
>
>修改为
>
>https://i2.wp.com/tvax4.sinaimg.cn/large/6f8a2832ly1gjqiig3g6uj22nh1ahto0.jpg

> 使用方法

```auto
https://i0.wp.com/telegra.ph/file/b5add9c8fd9a00edc62fa.jpg
https://cdn.cdnjson.com/so1.360tres.com/t01e8feab914bad8263.png
https://img.noobzone.ru/getimg.php?url=i.imgur.com/hWghm6oh.jpg
```

> 搜狗图片也有提供一个图片的外调接口

`https://img02.sogoucdn.com/v2/thumb/retype_exclude_gif/ext/auto/q/95/crop/xy/ai/t/0/?appid=122&url=`

临时用用可以，主要国内速度快，如果不可用，就自己在[搜狗图片搜索](https://pic.sogou.com/)，找到新的外调接口。

## 防盗链图片演示

```auto
http://pic1.zhimg.com/v2-8b657dff159debf1cff463d61b7dcafd_r.jpg
```

![1](https://i3.wp.com/pic1.zhimg.com/v2-8b657dff159debf1cff463d61b7dcafd_r.jpg "1")

该图片是知乎图片，存在防盗链直接贴在网页中无法显示，在图片外链前面加上图片镜像服务后可以正常显示了。

```auto
https://i.imgur.com/hWghm6oh.jpg
```

该图片是知名图床**imgur**的图片，至今已有10多年历史，由于上面不限制上传图片类型所以在中国无法打开，在图片外链前面加上图片镜像服务后就可以正常显示了。imgur可以用

```auto
https://img.noobzone.ru/getimg.php?url=
```

![图片防盗链最终解决方案](https://img.noobzone.ru/getimg.php?url=i.imgur.com/hWghm6oh.jpg "图片防盗链最终解决方案")

[https://images.weserv.nl/?url=](https://images.weserv.nl/?url=)

可当作备用，部分网站会无法使用。

## 相关推荐

+   [免费图床](/tools/图片空间/)


---

> 作者: [聪](/about)  
> URL: https://blog.funvip.live/tools/%E9%98%B2%E7%9B%97%E9%93%BE/  

