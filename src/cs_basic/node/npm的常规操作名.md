---
title: npm的常规操作名
date: 2024-02-08
tags:
  - npm
category: NodeJS
---

#### 查看/修改npm源

```bash
npm config get registry  // 查看npm当前镜像源  
npm config set registry https://registry.npm.taobao.org/  // 设置npm镜像源为淘宝镜像  
​  
yarn config get registry  // 查看yarn当前镜像源  
yarn config set registry https://registry.npm.taobao.org/  // 设置yarn镜像源为淘宝镜像
```


除了官方源,剩下的就是淘宝源和豆瓣源比较多了

#### 查看NPM全局的包
```
npm list -g --depth 0
```


![bf1198bad55349c0fc0321d064f36c6c](https://raw.githubusercontent.com/Xu-Hardy/image-host/master/bf1198bad55349c0fc0321d064f36c6c.png)

### npm清理缓存

```bash
npm cache clean -f
```

#### npm,yarn 与npm

在Node.js的生态系统中，`npm`、`yarn`和`pnpm`都是关键的包管理工具，它们各自以不同的方式优化了依赖管理和项目构建过程。理解它们之间的区别有助于开发者为自己的项目选择最合适的工具。

**npm**（Node Package Manager）是Node.js默认的包管理工具，提供了广泛的包注册中心和依赖管理功能。随着时间的发展，npm不断更新，增加了性能改进和新特性，例如`package-lock.json`文件用于确保依赖的一致性。

**yarn**由Facebook开发，作为npm的替代品在2016年推出。yarn引入了`yarn.lock`文件来锁定依赖版本，确保项目在不同环境中的一致性。此外，yarn的设计重点在于提高安装速度和依赖解析的效率。

**pnpm**是包管理工具中的后来者，专注于提升性能和空间效率。它通过使用硬链接和符号链接的方式来存储一份物理文件的多个引用，从而减少了重复下载和存储相同包的需求。这种方法显著减少了磁盘空间的占用，并加快了依赖安装的速度。

- **性能和空间效率**：pnpm通过硬链接和符号链接提供出色的空间效率和安装速度；yarn和npm在最新版本中也致力于提升性能，但pnpm在这方面具有天然优势。
    
- **依赖锁定**：yarn和npm使用锁文件来确保依赖版本的一致性；pnpm也提供类似机制，确保依赖的精确和安全。
    
- **社区和生态系统**：npm作为最早的包管理工具，享有最广泛的社区支持和生态系统；yarn凭借其创新性特性和大公司背景获得了快速增长；pnpm虽然是新选手，但因其独特的性能优势正在获得越来越多的关注。