---
title:        "ubuntu-install-wechat"
description:  "ubuntu系统安装微信客户端"
image:        "http://placehold.it/400x200"
author:       "Dong"
---

####准备工作  
   -在下载和运行这个项目之前，你需要在电脑上安装 Git 和 Node.js (来自 *[npm](https://www.npmjs.com/)*)。

####在命令行中输入:
   > 下载仓库
   >git clone https://github.com/geeeeeeeeek/electronic-wechat.git
   > 进入仓库
   >cd electronic-wechat
   > 安装依赖, 运行应用
   >npm install && npm start
   
####根据你的平台打包应用:
   >npm run build:osx
   >npm run build:linux
   >npm run build:win

####提示: 如果 npm install 下载缓慢，你可以使用 淘宝镜像([cnpm](https://npm.taobao.org/)) 替代 npm 。
   
####新渠道: 使用你熟悉的包管理工具安装。请查看*[社区贡献的镜像](https://github.com/geeeeeeeeek/electronic-wechat/wiki/System-Support-Matrix#%E7%A4%BE%E5%8C%BA%E8%B4%A1%E7%8C%AE%E7%9A%84%E5%AE%89%E8%A3%85%E5%8C%85)* 。
   
####新渠道: homebrew 安装也已支持 (更新至 electronic-wechat v1.2.0)！
   >brew cask install electronic-wechat

