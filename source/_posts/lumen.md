---
title: lumen建立API项目  
date: '2017-07-08 16:18'  
tags: php 框架 lumen API
---
#lumen环境搭建（5.4.X 版本）

## composer及lumen安装
环境: mac or linux

- 使用如下命令进行comoser的安装:  
1. curl -sS https://getcomposer.org/installer | php
2. mv composer.phar /usr/local/bin/  
3. 输入composer回车,能正常展示composer的版本及使用方法,即安装成功

<!-- more -->

- 使用如下命令进行lumen的项目创建及环境配置
1. composer create-project --prefer-dist laravel/lumen 项目名称  
   说明:  
   1) 时间可能会有些长,请耐心等待,如果长时间依然没有创建成功。  
   2) 请更换国内镜像或升级composer  
   更换国内镜像: composer config -g repo.packagist composer https://packagist.phpcomposer.com）  
   升级composer: composer selfupdate
   
2. 配置数据库信息:  
   lumen的项目配置信息都保存在.env文件中,修改相应的数据库配置信息:
   ```php
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1  【项目的mysql数据库服务器地址】
   DB_PORT=3306       【mysql对应的端口号】
   DB_DATABASE=mabei  【mysql的数据库名称】
   DB_USERNAME=root   【mysql的用户名】
   DB_PASSWORD=root   【mysql的密码】
   ```