---
layout: post
title: HarmonyOs2之真机调试
tag: Harmony OS
---

## Harmony OS 真机调试流程



> 按照目前的进度来讲，鸿蒙 2.0 的文档还是相当的简陋和结构混乱。
>
> 关于真机调试的步骤在我的部署之中，梳理如下：



### 手机端

如果进行手机作为调试工具，开发人员选项需要

* `HarmonyOs2` 系统

* 开启 `usb 调试`
* 保持唤醒状态（防止休眠）



### 电脑端



**安装 `DevEco` IDE，安装最新版的 `HarmonyOs SDK`**



#### 获取设备的 UUID

1. 找到 `HarmonyOs SDK` 的目录位置，一般在 `C:\Users\Administrator\AppData\Local\Huawei\Sdk`
2. 手机开发者选项陪之后，链接到电脑
3. 进入 `toolchains`  目录，打开 `powershell` ，输入 `.\hdc.exe shell bm get -u`，得到 `UUID`



#### Harmony OS 签名加密



##### Step1 ：生成签名文件和请求文件

创建项目完成后，点击 `Build > Generrate key and csr`

![20210821-170125-0676.png](https://gitee.com/immcc/images/raw/master/blog/20210821-170125-0676.png)

**创建完成之后，你会得到 `.p12` 和 `.csr` 文件，保存好这是编译 hap 包调试的关键**



##### Setp2 : App Gallery Connect 申请证书

[AppGallery Connect (huawei.com)](https://developer.huawei.com/consumer/cn/service/josp/agc/index.html#/ups/9249519184596237889)

![20210821-171025-0174.png](https://gitee.com/immcc/images/raw/master/blog/20210821-171025-0174.png)



**Setp3 : AGC 创建项目 > 应用**

​	[https://developer.huawei.com/consumer/cn/service/josp/agc/index.html#/myProject](https://developer.huawei.com/consumer/cn/service/josp/agc/index.html#/myProject)



#### 回到项目本身

1. 修改 `config.json` 文件
   	`budleName` 和 `AGC 项目`名必须一致，删掉 `apiVersion.releaseType`
2. 配置签名文件
   	`File > Project Structure > Models > entry > Signing Configs > debug`
3. 编译 hap 包
   	`build > build Hap(s)/App(s)`
      	如果这个地方是灰色的，点击 `File > Sync Project with Gradle files`
      	如果下载的项目已经包含了 `.gradle` 目录，进行手动删除