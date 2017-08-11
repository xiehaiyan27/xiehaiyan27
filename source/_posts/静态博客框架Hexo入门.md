---
title: 静态博客框架Hexo入门
author:
tags:
categories:
    - Web技术
thumbnail:
blogexcerpt: 不过，现在网上一搜都会搜到很多关于hexo的一些文章，所以想更加地了解 hexo 和获取其主题可以网上找找。 
---
## hexo 简介

>简单地说，Hexo 是一个基于 Node.js 的轻量的静态博客框架。官网如下：

>官网链接：https://hexo.io/

![Hexo](http://7xs305.com1.z0.glb.clouddn.com/2132683522.png "hexo官网")

>Github 主页：https://github.com/hexojs/hexo

>不过，现在网上一搜都会搜到很多关于hexo的一些文章，所以想更加地了解 hexo 和获取其主题可以网上找找。

## hexo 特性

- Blazing Fast —— 速度快——几百篇文章也可以秒生成；
- Markdown Support —— 支持 GitHub Flavored Markdown 和所有 Octopress 的插件；
- One-Command Deployment —— 需要一个命令就可以配置您的网站 GitHub 页面， Heroku 或其他网站；
- Various Plugins —— Hexo 支持 EJS 、Swig和Stylus。通过插件支持 Haml、Jade 和 Less。


## hexo 特性

- Blazing Fast —— 速度快——几百篇文章也可以秒生成；
- Markdown Support —— 支持 GitHub Flavored Markdown 和所有 Octopress 的插件；
- One-Command Deployment —— 需要一个命令就可以配置您的网站 GitHub 页面， Heroku 或其他网站；
- Various Plugins —— Hexo 支持 EJS 、Swig和Stylus。通过插件支持 Haml、Jade 和 Less。

## hexo 使用

#### hexo 安装

<p>首先，在安装 hexo 之前，你要先安装 Node.js 和 Git ，具体下载和安装请访问它们的官网。</p>
<p>接下来，安装 hexo ：</p>
<pre><code>$ npm install -g hexo-cli
</code></pre>

#### hexo初始化
<p>初始化指定目录，会在目前的文件夹建立一个名为 的新文件夹；否则会在目前文件夹初始化。</p>
<pre><code>1   $ hexo init &lt;folder&gt;
2   $ cd &lt;folder&gt;
3   $ npm install
</code></pre>
<p>来看一下我们安装完之后 hexo 的目录结构是如下这样的：</p>
<pre><code>
1   ├── _config.yml
2   ├── package.json
3   ├── scaffolds
4   ├── scripts
5   ├── source
6   |   ├── _drafts
7   |   └── _posts
8   └── themes
9.
</code></pre>
>看起来更加直观，在这里我截一个我自己的目录图：
![查看图片](http://7xs305.com1.z0.glb.clouddn.com/2344787021.jpg "查看图片")
>目录结构作用在这里简单的介绍一下：

+	_config.yml 文件 —- 为网站配置文件；
+	package.json 文件 —- 项目模块描述；
+	source 目录 —- 创建博客文章的源目录，后面有说到这个；
+	public 目录 —- 静态资源，就是我们直接可以访问的一些资源，这些资源在执行 hexo generate 命令后生成；
+	themes 目录 —- 放置博客主题，就像WordPress、typecho这些博客程序都是有一个专门用来放置主体的目录，如果一个博客程序没这个功能，那未免也太过于单调，对吧。

##	创建新博客
			1	$ hexo new "中国移动-139邮箱" # 创建文章 post
			2	$ hexo new page "about"     # 创建页面 page
创建博客或文章会在 /source/_posts/ 下生成后缀为 .md 的文件，我们可以这个文件上编写我们想要发表的文章或博客，hexo 支持 markdown 语法，很方便快捷。
###	生成博客
		1	$ hexo generate  # 或者 hexo g
生成博客这一步也叫编译，讲写好的 .md 内容生成到 public 目录去，也就是后面运行服务器之后直接访问的东西。
###	运行服务器
		1	$ hexo server # 或者 hexo s
注意：

+	服务器默认会跑在 http://localhost:port （port 默认为 4000端口，可在 _config.yml 设置）；
+	hexo 所依赖的模块参考如下：

![依赖模块](http://7xs305.com1.z0.glb.clouddn.com/452712668.png	"依赖模块")
### 部署
 
编译完博客之后，可以生成的博客内容（静态页面）部署到 github，如果你嫌 github 访问速度比较慢的话，coding 是一个不错的选择。下面是以部署至 github 为例，做简单介绍。
 
首先，现在 github 上创建一个新的 repository，（假设，项目名为 jangdelong ）创建好之后，会生成一个 git 项目地址；
 
把创建好的 github repository 的 git 地址配置到 hexo 目录下的 _config.yml 的配置文件中；
 
    1   deploy:
    2       type: git
    3       message: 博客更新 -- at {{ now('YYYY-MM-DD HH:mm:ss') 4}}
    5       repository:                             
 
    6       https://github.com/jangdelong/jangdelong.github.com.gitbranch: maste
执行 hexo deploy 或者 hexo d 即可部署；  
部署完之后，浏览器地址栏输入 jangdelong.github.io 即可访问。
###	参考

*	hexo官网：https://hexo.io/；
*	http://segmentfault.com/a/1190000000370778；
*	http://segmentfault.com/a/1190000002538363。