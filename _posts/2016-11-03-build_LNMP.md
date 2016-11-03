---
title:        "LNMP"
description:  "ubuntu 16.04 系统下搭建LNMP开发环境"
image:        "http://placehold.it/400x200"
author:       "Dong"
---

准备工作
------

默认你已安装了ubuntu 16.04系统

>LNMP (PHP7.0+Mysql5.7+Nginx1.10)

步骤开始
----
首先更新源

>sudo apt-get update

**1.安装mysql**

>sudo apt-get install mysql-server

**2.安装nginx**

>sudo apt-get install nginx   

安装好nginx，打开浏览器输入 [localhost](http://localhost)    看到 Welcome to nginx！ 说明安装成功了。

修改nginx配置站点
 
>sudo vim /etc/nginx/sites-available/default

如果没有安装vim,请先安装(已安装请忽略)

>sudo apt-get install vim

下图为参考
![示例](/resources/font-awesome/img/Lnmp/nginx.png)
listen 设置网站访问端口号

root 后面的路径表示监听的站点->就是网站路径  

server_name 设置访问网站域名或者ip

把fastcgi_pass和include snippets/fastcgi-php.conf;前面的#去掉

如果想配置多站点,就复制server{  }多一份粘贴就好

配置完重新启动nginx:  

>sudo service nginx reload


**3.安装php7.0-fpm**

>sudo apt-get install php7.0-fpm 

安装php 7.0  安装其他版本也是一样的。

在刚配置完的站点目录下，新建个index.php测试下看看
 
 
>phpinfo();

![示例](/resources/font-awesome/img/Lnmp/phpinfo.png)

看到此图说明已近配置成功了，下面还需要安装一些常用的扩展库

>sudo apt install php-mysql php-curl php-mcrypt php-gd php-memcached php-redis  
   
此方式安装会同时在多个版本下面分别安装还有一些库   

> sudo apt install php7.0  按tab 可以显示如下一些库 
 
 
    php7.0            php7.0-fpm        php7.0-mysql      php7.0-sqlite3
    php7.0-bcmath     php7.0-gd         php7.0-odbc       php7.0-sybase
    php7.0-bz2        php7.0-gmp        php7.0-opcache    php7.0-tidy
    php7.0-cgi        php7.0-imap       php7.0-pgsql      php7.0-xml
    php7.0-cli        php7.0-interbase  php7.0-phpdbg     php7.0-xmlrpc
    php7.0-common     php7.0-intl       php7.0-pspell     php7.0-xsl
    php7.0-curl       php7.0-json       php7.0-readline   php7.0-zip
    php7.0-dba        php7.0-ldap       php7.0-recode    
    php7.0-dev        php7.0-mbstring   php7.0-snmp      
    php7.0-enchant    php7.0-mcrypt     php7.0-soap

如果扩展安装完就可以进行开发了

在这里也写一下phpstorm 10的安装

1.首先在**[Jetbrains官网](https://www.jetbrains.com/phpstorm/download/#section=linux-version)**下载PhpStorm的tar包．如果你偏爱命令行，那么可以使用wget来下载tar包

![示例](/resources/font-awesome/img/Lnmp/phpstorm.png)

2.安装jdk(phpstorm必须要jdk环境才能运行)  

    1.下载jdk   
  
        http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html
  
    2.解压压缩包
  
        sduo tar zxvf  文件名
  
        修改目录名称
  
        sudo mv   源目录名/   新目录名/   
  
    3.配置环境变量
  
        创建文件/etc/profile.d/development.sh，将下面的内容复制到该文件。
   
        export JAVA_HOME=/usr/local/development/jdk1.7.0_04  
        export JRE_HOME=$JAVA_HOME/jre  
        export CLASSPATH=.:$JAVA_HOME/lib:$JRE_HOME/lib:$CLASSPATH  
        export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$PATH  
   
    4.重启电脑  使用命令 java  -version 测试
  
3.安装:打开一个终端窗口．将工作目录切换到下载目录，然后解压下载好的tar.gz文件．
  
>tar xvf PhpStorm-2016.1.tar.gz

在当前的工作目录下会生成一个新的目录，PhpStorm-145.258.2．为了保持系统整洁有序，我们把这个目录移到/opt/目录下．

>sudo mv PhpStorm-145.258.2/ /opt/phpstorm/

现在，创建一个软链接．

>sudo ln -s /opt/phpstorm/bin/phpstorm.sh /usr/local/bin/phpstorm

然后，在终端里输入phpstorm命令来启动PhpStorm程序．

>sudo ./PhpStorm-2016.2.1/bin/PhpStorm.sh

到此为止
