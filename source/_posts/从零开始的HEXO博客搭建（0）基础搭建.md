---
title: 从零开始的HEXO博客搭建（0）基础搭建
date: 2025-04-03 22:30:11
tags:
---

***（待更新）***

## 前言

本文章为 Windows 用户编写，同样适用于 macOS，Linux。

在搭建博客时，请记得保存过程中的截图，未来你很可能会需要它们来撰写一篇详细的教程。

## 准备工作

可以前往 [Hexo 官方文档](https://hexo.io/zh-cn/docs/#%E5%AE%89%E8%A3%85) 查询 Hexo 安装教程。

### 安装 Git

我们使用 Git 管理我们的博客，前往 [Git 官方网站](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git) 安装 Git。

### 安装 Hexo

Hexo 是我们博客所使用的框架。

Hexo 基于 Node.js，为了使用 Hexo，首先前往 [Node.js 官方网站](https://nodejs.org/zh-cn/download/prebuilt-installer) 安装 Node.js。

>安装后建议通过命令
>
>```powershell
>npm config set registry https://registry.npmmirror.com
>```
>
>切换 Node.js 镜像源以防止网络问题。

安装完毕后，通过指令

```powershell
npm install -g hexo-cli
```

安装 Hexo。

### 安装 VSCode

我们使用 Visual Studio Code 来编辑博客。

前往 [VSCode 官方网站](https://code.visualstudio.com/download) 安装 VSCode。

## 初始搭建

### 本地初始化

新建一个文件夹。在文件夹中打开 VSCode。

在 VSCode 的终端中执行以下命令：

```powershell
git init  # 初始化本地 git 储存库

hexo init # 初始化本地 Hexo
npm install # 安装依赖
```

完成后输入下列命令，生成静态文件：

```powershell
hexo g  # hexo generate
```

完成后输入下面命令，启动本地服务器进行预览：

```powershell
hexo s  # hexo server
```

打开终端中的链接。出现 Hexo 的默认页面，这说明你已经成功在本地初始化博客。

### 推送至 GitHub Pages

#### GitHub 相关设置

在 <https://github.com/new> 创建新仓库`{你的用户名}.github.io`。

#### 本地相关设置

首先安装 hexo-deployer-git：

```powershell
npm install hexo-deployer-git --save
```

修改 _config.yml 文件。在文件末尾找到 ```development``` 部分，修改为：

```powershell
deploy:
  type: git
  repo: https://github.com/{你的用户名}/{你的用户名}.github.io.git
  branch: main
```
