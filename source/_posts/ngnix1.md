---
title: nginx之旅
date: '2017-05-19 21:17'
tags: nginx 学习 负载均衡 配置
---

# nginx配置

## 文件路径配置

- 访问首页

  > 语法： index file1 file2 file3 ... ;<br>
  > 配置块： http, server, location

- HTTP错误码重定向页面

  > 语法： error_page code[code1 code2 ...][=|answer_code=]uri|@named_location;<br>
  > 配置块： http, server, location, if

- 是否允许递归使用error_page

  > 语法： recursive_error_page [on|off];<br>
  > 配置块： http，server，location

- try_files

## 内存及磁盘资源分配

- HTTP包体只存储到磁盘文件中

  > 语法： client_body_only_in_file on|off|clean;<br>
  > 配置块： http，server，location

- HTTP包体尽量写到一个内存buffer中

  > 语法： client_body_in_single_buffer size;<br>
  > 配置块： http，server

- 存储超大HTTP头部的内存buffer的大小

  > 语法： large_client_header_buffers number size;<br>
  > 配置块： http，server

- 存储HTTP包体的内存buffer的大小

  > 语法： large_client_body_buffer_size size;<br>
  > 配置块： http，server，location

- HTTP的临时存放目录

  > 语法： client_body_temp_path dirpath[level1[level2[level2]]];<br>
  > 配置块： http，server，location

- 建立TCP链接预配内存池初始化大小

  > 语法： connect_pool_size size;<br>
  > 配置块： http，server

- 请求预配内存池大小

  > 语法: request_pool_size size;<br>
  > 配置块: http, server

## 网络连接的设置

- 读取HTTP头部的超时时间

  > 语法: client_header_timeout time;（默认单位:秒）<br>
  > 配置块: http, server, location

- 读取HTTP包体的超时时间

  > 语法: client_body_timeout time;（默认单位:秒）<br>
  > 配置块: http, server, location

- 发送响应的超时时间

  > 语法: send_timeout time;<br>
  > 配置块: http, server, location

- 发送RST包来重置连接

  > 语法: reset_timeout_connection on|off;<br>
  > 配置块: http, server, location

- 关闭用户的连接方式

  > 语法： lingering_close on|off|always<br>
  > 配置块： http, server, location

- 关闭用户的链接方式的延迟时间

  > 语法： lingering_time time;<br>
  > 配置块： http, server, location

- 无数据情况下关闭用户链接的超时时间

  > 语法： lingering_timeout time;<br>
  > 配置块： http, server, location

- 禁用多个http请求复用同一个http长链接（禁用keepalive功能）

  > 语法： keepalive_disable [msie6|safria|none]...;<br>
  > 配饰块： http, server, location

- keepalive超时时间

  > 语法： keepalive_timeout time;<br>
  > 配置块： http, server, location

- 一个keepalive长连接上允许承载的最大请求数

  > 语法： keepalive_requests n;<br>
  > 配置块： http, server, location

- 对keepalive是否启用TCP_NODELAY选项

  > 语法： tcp_nodelay on|off;<br>
  > 配置块： http, server, location

- 是否开启FreeBSD系统上的TCP_NOPUSH或linux系统上的TCP_CORK功能

  > 语法： tcp_nopush on|off;<br>
  > 配置块： http, server, location

## MIME类型的设置

- MIME type与文件扩展映射
> 语法： type {...};<br>
配置块： http, server, location
