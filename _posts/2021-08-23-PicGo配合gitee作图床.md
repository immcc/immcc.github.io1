---
layout: post
title: Gitee作图床很舒适了
tag: gitee
---

> 之前使用的是 `utools` 中的 `filebed` 上传到 `gitee` 中，今天改了名字突然之间就配置不成功了;
>
> 然后找到了 `PicGo` ，在配置完成后发现 `Typora` + `PicGo` +`Gitee` 的组合非常完美！
>
> 为什么不用 `github`，因为 `github` 的速度是非常的慢的！

## Gitee

`gitee` 端的配置非常简单，分为两步：第一创建仓库，第二创建私人令牌

`gitee` 端要配置一个存储仓库，例如 `images`

![image-20210823173908666](https://gitee.com/immcc/images/raw/master/blog/202108231739728.png)



然后创建私人令牌，获取 `token`

![](https://gitee.com/immcc/images/raw/master/blog/202108231737082.png)



**拿到`token`之后，`gitee`端到这里就结束了**

## PicGo

`PicGo` 端分为三步：

一、下载 `gitee uploader` 上传插件

![image-20210823174318818](https://gitee.com/immcc/images/raw/master/blog/202108231743862.png)

二、图床配置

![image-20210823174627388](https://gitee.com/immcc/images/raw/master/blog/202108231746446.png)



## Typora

对 `Typora` 进行偏好设置，非常简单。

当你进行插入图片的时候，`PicGo` 会弹窗确认是否上传，确认后会把回调后的地址插入 `markdown`，

![image-20210823175206478](https://gitee.com/immcc/images/raw/master/blog/202108231752515.png)

例如下图：

```markdown
![image-20210823174756123](https://gitee.com/immcc/images/raw/master/blog/202108231747179.png)
```

![image-20210823174756123](https://gitee.com/immcc/images/raw/master/blog/202108231747179.png)

