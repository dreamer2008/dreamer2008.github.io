# Github Blogging with Hexo

  
  现在github非常火，很多人（包括很多爱写作的非程序猿）都在上面开博了。推荐两篇文章：
  
  * [为什么你要写博客？](http://zhuanlan.zhihu.com/cnfeat/19743861)

  * [我为什么坚持写博客？](http://stormzhang.com/android/2016/03/04/why-i-keep-writing-blog/)
  
    
  工具方面，从基于Ruby的Jekyll，Octopress，到基于Python的Pelican，再到基于Node.js的Hexo。经过试用，我最终选择了Hexo。更多的工具，请看[这里](http://www.tuicool.com/articles/rmyuEnm)。

  ## Hexo 简介
  
  [Hexo](http://hexo.io/)出自一个台湾大学生[tommy351](https://github.com/tommy351)之手（原来我们大中华区也有世界级的编程牛人啊。赞一个！）。

  Hexo是一个快速的、强大的Blog框架，主要是由 Node.js 构建出来的。同时支持多线程生成，上百个文件只需要花数秒中就能生成。
  
  Hexo还支持GitHub Flavored Markdown 和所有的 Octopress 插件和 高兼容 Jekyll/Octopress。

  ## Hexo 安装
 
  Hexo 是一个轻量的静态博客框架。通过Hexo可以快速生成一个静态博客框架,仅需要几条命令就可以完成,相当方便。

  * 安装Git和Node.js

  * 安装和配置Hexo

  * 申请github账号

  * 编写和发布博客

  具体可以参考这几篇文章：
  * [如何搭建一个独立博客](http://www.jianshu.com/p/05289a4bc8b2)

  * [Hexo 3.0 静态博客使用指南](http://www.jianshu.com/p/73779eacb494)
  * [hexo你的博客](http://ibruce.info/2013/11/22/hexo-your-blog/)
  * [hexo系列教程](http://zipperary.com/2013/05/28/hexo-guide-2/)

  <!--more-->

  ## 问题及其解决

  ### npm install运行缓慢或失败

  可以指定国内的镜像网站，请参考[这里](https://cnodejs.org/topic/4f9904f9407edba21468f31e)

  ### 中文的支持问题

  * 在根目录的_config.yml中配置中文
  ``` bash
  language: zh-CN
  ```
  * 保存文件的时候，要确保文件是UTF-8编码

  ### 其他问题
  请参考：http://wp.huangshiyang.com/hexo常见问题解决方案

  ## Hexo常用命令
   ``` bash
   hexo n ==  hexo new

   hexo g ==  hexo generate

   hexo d ==  hexo deploy

   hexo s ==  hexo server
   ```
   其他常用命令，请参考[这里](http://segmentfault.com/a/1190000002632530)。

  ## github域名绑定问题

  请参考前面的文章。

  ## Hexo的Theme（主题/皮肤）
   
   定制皮肤需要一定的Web前端基础（HTML/DIV/CSS/JavaScript）。[更多主题，总有一款适合你](https://github.com/hexojs/hexo/wiki/Themes)。

  ## Markdown语法

  .md文件用纯文本软件编辑即可。这里有几个入门教程：
  
  * [Markdown](http://daringfireball.net/projects/markdown/)

  * [为什么我们要学习 Markdown 的三个理由](http://www.oschina.net/news/28122/reasons-we-should-learn-markdown)
  
  * [认识与入门 Markdown](http://sspai.com/25137)

  * [献给写作者的 Markdown](http://www.jianshu.com/p/q81RER)

  * [Markdown语法说明](http://wowubuntu.com/markdown/)


  


