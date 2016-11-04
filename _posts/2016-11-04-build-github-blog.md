---
title:        "github-blog"
description:  "ubuntu系统下搭建github博客"
image:        "http://placehold.it/400x200"
author:       "Dong"
---

##准备工作  
   - 申请一个github帐号
   - 安装git

####为什么要用jekyll来重新部署博客？我简单的总结了一下：
   * 流行又简洁的MarkDown写作语法
   * 轻量级的网站结构，不再有动态网站的沉重
   * 方便的和github pages结合，不仅免费，而且方便
   
###1.在github新建一个仓库(repository)注意命名规则
![示例](/resources/font-awesome/img/github-blog/creat_repository.png)
![示例](/resources/font-awesome/img/github-blog/fill_detail.png)

###2. 进入项目设置页面, 因为这个项目就是专门的放页面的,所以master分支即可. 如果是你的某个仓库的页面,你需要设置到 gh-pages 分支中.
![示例](/resources/font-awesome/img/github-blog/toSetting.png)
![示例](/resources/font-awesome/img/github-blog/setting_detail.png)
![示例](/resources/font-awesome/img/github-blog/setting1.png)

###3.之后我们就要在本地部署jekyll， 首先你需要ruby来使用本地jekyll。安装ruby。  
   可以直接使用两个命令完成Ruby的安装。
   
   >sudo apt-get update  
   >sudo apt-get install ruby  
   >sudo apt-get install rubygems  
   >export PATH=$PATH:$HOME/bin:/var/lib/gems/1.8/bin  
   
   安装jekyll。建议换成淘宝服务器：
   
   >sudo gem sources --remove http://rubygems.org/  
   >sudo gem sources -a https://ruby.taobao.org/
   
   查看当前设置的服务器
   
   >sudo gem sources -l
   
   安装Jekyll
   
   >sudo apt-get install jekyll  
   
   jekyll目录
![示例](/resources/font-awesome/img/github-blog/jekyll_mb.png)

###4.在本地新建项目文件夹
>jekyll new 名字  

下载一个jekyll模板,然后把模板文件解压到项目文件夹下,**注意配置_config.yml**,_posts就是写博客的文件,后缀.md或者.markdown,命名规则(yyyy-mm-dd-名字.md),layout必须为post,查看效果请在项目文件夹下运行命令行  

>jekyll serve  

在浏览器输入地址:localhost:4000,就可以看到效果

在这里推荐一个快速入门学习markdown语法的[网址](http://www.ituring.com.cn/article/23)

###5.上传到github仓库
>git add .  
>git commit -m "注释"  
>git push origin master

然后在浏览器上输入网址,你在setting置好的名字,就可以看到自己的博客
![示例](/resources/font-awesome/img/github-blog/address.png)

到此为止,下面就可以开始写博客了

