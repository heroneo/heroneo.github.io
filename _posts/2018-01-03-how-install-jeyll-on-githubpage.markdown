---
layout: post
title: 使用Jeyll在Github Page上部署个人博客 
date: 2018-01-03 16:41:20.000000000  +09:00
category:  tech
tags: Jekyll on githubPage
---

#### 前言
目前网上（尤其是在github上）的博客主要以技术博客为主，但作为记录和反思自己想法的一种有效手段，每天记录输出自己的学习或思考还是很有益处的，推荐每一个人试着去做。本文记录如何在使用Jeyll和github部署自己的博客站点，以及简单的使用Sublime Text + github desktop进行发博文的操作，有同样需求的人可作参考。


#### 准备工作
自建博客站点有几个部分需要准备：

* _博客程序（Jekyll)_

    首先是博客平台本身，这里使用[Jekyll](https://www.jekyll.com.cn "Jekyll中文网站")。Jekyll是什么？它是一个简单静态博客生成工具，它不需要数据库，直接写（Markdown)文档放进去，它就可以自动生成Html网页显示出来。我们只需要专注于写文章，不用考虑站点维护和内容排版。

* _服务器与域名 (Github Page)_

    很显然，要把博客放上互联网，需要存放到联网的主机并设置域名让别人可以访问。庆幸的是就我们简单的需求而言，github提供了免费的[Github Page](https://pages.github.com "Github Page")服务，能直接运行我们的Jekyll程序，而且有一个不错的二级域名（username.github.io)能用，可以说是再好不过的选择了。

* _文章更新管理（Sublime Text + Github Desktop）_
    
    因为Jekyll的博文其实就是文本文件，在github page上可以像管理代码内容一样对其进行操作和管理。你可以使用自己喜欢的编辑器来写文章（鉴于不错的md插件和用户体验,我们这里选择用[Sublime Text](https://www.sublimetext.com "sublimetext官网")编辑器）。用编辑器写好的文章保存为markdown格式文本，然后通过[Github Desktop](https://desktop.github.com "github Desktop")客户端把文本上传到Github Page上（如果乐意你也可以直接用git命令操作），这样就完成了文章的添加与更新。 

#### 操作步骤
 1.  __开通Github Page__  
    * [注册github账号](https://github.com "github首页")  
    * 登录后新建个人主页的仓库。  
      _这里要注意的是仓库名称，比如你的帐号如果是john，那么仓库名称应该是：john.github.io_  
      ![新建个人主页仓库](http://img.blog.csdn.net/20160617152346289 "新建仓库")  
         _本图为引用自网络，[原图片地址](http://blog.csdn.net/yanzhenjie1003/article/details/51703370 "图片出处地址")_

2. __将Jekyll添加到个人主页仓库__      
    * 使用Github Desktop将仓库clone到本地    
    ![clone到本地](https://wx4.sinaimg.cn/mw1024/6587fba0gy1fn3gmvftpwj20bz05vt99.jpg "clone")  
    * 因为Github Page原生支持Jekyll，我们找一个喜欢的Jekyll主题模版程序直接用。这里用了[喵神](http://www.onevcat.com/#blog "onevcat")共享的[Vno - Jekyll](https://github.com/onevcat/vno-jekyll "Vno-Jekyll")。 把主题文件commit push到我们刚才新建的仓库，把文件放入本地库，然后使用  
     ![new repository](https://wx3.sinaimg.cn/mw1024/6587fba0gy1fn3h9l2rrij20qo0icdh0.jpg "newRepository")  
    * 根据需求修改配置文件`_config.yml`。里面的参数意思可以直接查看[Jekyll网站](https://www.jekyll.com.cn "Jekyll中文网站")的说明或自己摸索。

3. __访问和更新__
    * 现在我们使用Github Page提供的二级域名`https://你的用户名.github.io`就可以访问博客了。  
    * 如果要新建文章，只需在编辑器里写好markdown格式的文本文件，放到**_posts**文件夹中，通过上面第2步骤commit push到仓库里就可以。但需要注意一点，文件的名称要严格按照Jekyll的示范文件命名: `年-月-日-标题.MARKDOWN`，例如`2018-01-03-how-to-write-a-blog.markdown`,如果名称格式不对Jekyll无法正确转换成html。

#### 注意事项
*  如果你看下文章（post)会发现，每个文件顶部都有__YAML头信息__。头信息必需在文件的开始部分，并且需要按照 YAML 的格式写在两行三虚线之间。下面是一个基本的例子：
`---  
layout: post  
title: Blogging Like a Hacker  
category:  技术  
tags: Jekyll  
---`  
基本上每篇文章复制过来改下title等信息即可，想要进一步了解请移步[官方文档](https://www.jekyll.com.cn/docs/frontmatter/ "Jeykll")

*  __markdown__本身的写法比较简单，语法可参考[地址](https://daringfireball.net/projects/markdown/dingus "markdown-dingus"),也可以搜索其他网络教程。










