---
title: WebDav访问阿里云
categories: NAS
tags:
  - WebDav
date: 2024-02-15
---
宣称从来不限速的阿里云也开始宣称限速了,无论你的宽带是多少,在阿里云上下载的速度仍然是2-3M/S,尽管这个速度已经比百度网盘快速很多,但是仍然不能利用全部的带宽.

那么可以把阿里云转换成WebDav然后使用客户端挂载,然后下载可以跑慢本地的带宽.这个是一个开源的项目,作者对上传功能不保证一定可以使用.项目Github在此:https://github.com/messense/aliyundrive-webdav

我这里使用了pypi的包进行的安装,成功之后可以使用二进制文件启动,看起来比docker的方式要简单一些

```bash
pip install aliyundrive-webdav
```

由于M系列芯片的8080端口被占用,我更改了这个服务的启动端口,同时也设置了用户名和密码

```bash
aliyundrive-webdav -P 8081 -U admin -W admin
```

这个是挂载成功的结果:

![image-20240215151618353](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/image-20240215151618353.png)

一开始连接webdav总有延迟,换了一个小点的目录能更快的刷出来数据,猜测是同步元数据什么的,另外文件夹虽然在webdav中点开没有数据,但是确实可以下载下来,也可以跑慢网速



服务端日志一直会有重试机制,尽管不耽误使用...

![image-20240215151704436](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/image-20240215151704436.png)



总结下,之前几年感觉网上炒的很火的教程其实并没有完全完善,最好还是找一个服务器以守护进程的方式启动这个转换程序,个人的笔电部署服务端总需要重启服务,长时间等待加载可能不可避免.
