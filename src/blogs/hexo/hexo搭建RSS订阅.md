---
title: Hexo RSS订阅
tags:
  - blog
categories: HEXO
date: 2023-01-25 00:00:00
---

给HEXO博客搭建RSS功能，先安装依赖






```bash
npm install --save hexo-generator-feed
```

<!--more-->

> [!note]
> 注释文字




$$
a^2
$$

> [!note]
> 注释文字

> [!important]
> 重要文字

> [!tip]
> 提示文字

> [!warning]
> 注意文字

> [!caution]
> 警告文字



嵌套可以通过增加外层容器的 marker 数量完成:

::: important
重要容器。
:::

::: info
信息容器。
:::

::: note
注释容器。
:::

::: tip
提示容器
:::

::: warning
警告容器
:::

::: caution
危险容器
:::

::: details
详情容器
:::







然后在 hexo 根目录下的 `_config.yml` 文件中添加配置，用来开启

```yaml
feed:
    type: atom
    path: atom.xml
    limit: 20
```

然后在 theme 目录下的 `_config.yml` 文件中添加配置, 调试和部署模式可以看到效果

```yaml
social_links:
	rss: /atom.xml
```



使用RSS阅读器也可以订阅

![](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/20230125145832.png)

参考：

https://wxnacy.com/2018/12/12/hexo-add-rss/

https://blog.haysc.tech/hexo-feed-setup/

https://sspai.com/post/56079

