---
title: Netlify部署静态网站
categories: Front End
tags:
  - GIT
  - Front-end
date: 2018-09-30 17:25:30
---

Netlify提供了非常直观的方式来部署和更新静态网站。通常，网站是通过连接到GitHub、GitLab或Bitbucket仓库自动部署的。每当你推送更改到相关分支时，Netlify都会自动检测到这些更改并重新部署网站。

但如果你需要手动更新静态网站，以下是一些方法：

1. **通过Git触发部署**：
    - 对于已经与Git仓库连接的项目，只需提交并推送更改到关联的分支。Netlify将自动检测更改并开始新的构建和部署过程。

2. **手动拖放文件**：
    - 如果你不想通过Git部署，Netlify提供了一个拖放界面，允许你手动上传网站的预构建版本。
    - 登录到Netlify Dashboard。
    - 选择你的网站项目。
    - 转到"Deploys"选项卡。
    - 在页面顶部，你会看到一个区域，提示你"Drag & drop your site output folder here"。直接拖放你的构建文件夹（例如`dist`或`public`）到这里即可开始部署。

3. **使用Netlify CLI**：
    - 使用Netlify的命令行工具，你可以从本地环境手动触发部署。
    - 首先，你需要安装CLI：`npm install netlify-cli -g`
    - 然后，登录：`netlify login`
    - 在你的静态网站的根目录，使用`netlify deploy`命令来部署。

4. **清除缓存并重新部署**：
    - 如果你认为缓存可能是问题，你可以选择"Clear cache and deploy site"来强制Netlify清除缓存并从头开始构建和部署。
    - 在Netlify Dashboard的"Deploys"选项卡，点击"Trigger deploy"下拉按钮，然后选择"Clear cache and deploy site"。

确保每次手动部署后，都检查部署的日志和输出，以确保没有错误或问题。