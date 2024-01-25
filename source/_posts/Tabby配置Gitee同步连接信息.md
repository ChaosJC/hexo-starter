---
title: Tabby配置Gitee同步连接信息
tags: [tabby]
categories: [工具]
poster:
  headline: Tabby配置Gitee同步连接信息
  color: white
date: 2024-01-11 07:51:05
description:
cover: https://file.zfjyc.cn/file/static/b3698dea6520b70d4c4b_repeat_1706149707777__853124.png
banner: 
pin: true
---

## 一、Tabby安装sync-config插件

在设置>插件中搜索sync-config并安装，安装成功后重启一下Tabby使插件生效。

![安装sync-config插件](https://file.zfjyc.cn/file/blog/image-20240110205246124.png)



## 二、配置Gitee获取私人令牌和Gists地址

1. 生成私人令牌，打开https://gitee.com/ ，点击右上角头像在下拉框中点击设置>私人令牌>生成新令牌 。

   ![生成私人令牌](https://file.zfjyc.cn/file/blog/image-20240110205849531.png)

2. 令牌描述随便填，权限勾选gists，然后点击提交后输入密码验证，验证通过后即可看到令牌，点击复制后面要用。

   ![image-20240110212436142](https://file.zfjyc.cn/file/blog/image-20240110212436142.png)

   ![生成令牌](https://file.zfjyc.cn/file/blog/image-20240110210946839.png)

3. 生成gists文件，点击头像左边的“＋”，选择”发布代码片段“，下面内容按要求填写即可。

   ![生成gists](https://file.zfjyc.cn/file/blog/image-20240110211657547.png)

4. 发布之后会进到gists详情页，复制地址栏路径最后一级。

   ![gists](https://file.zfjyc.cn/file/blog/image-20240110212059299.png)

## 三、配置Tabby同步

回到Tabby，在设置中找到Sync Config，按要求填写Token和GIst，点击Upload config上传配置，看到success即可。在其他电脑上同样配置后就可以在不同设备间同步连接信息。

![同步配置](https://file.zfjyc.cn/file/blog/image-20240110212727859.png)