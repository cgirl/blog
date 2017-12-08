---
title: nginx之旅
date: '2017-07-13 21:17'
tags: nginx 学习 负载均衡 配置
---

# nginx配置

## 文件路径配置

- 访问首页

  > 语法： index file1 file2 file3 ... ;<br>
  > 配置块： http, server, location

<!-- more -->

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
> 配置块： http, server, location

- 默认MIME type
 > 语法: default_type MIME-type;  
 > 配置块: http, server, location

- MIME type散列桶占用内存的大小
 > 语法: types_hash_bucket_size size;  
 > 配置块: http, server, location

- MIME type散列桶占用最大内存的大小
 > 语法: type_hash_max_size size;  
 > 配置块: http, server, location

## 对客户端请求的限制
- 按HTTP方法名限制用户请求
 > 语法: limit_except method ... {...};  
 > 配置块: location

- HTTP请求包体的最大值
 > 语法: clinet_max_body_size size;
 > 配置块: http、server、location

- 对请求的速度
 > 语法: limit_rate speed;
 > 配置块: http、server、location、if

- 对请求限速的延迟市场
> 语法: limit_rate_after time;  
> 配置块: http、server、location、if


## 文件操作的优化
- sendfile系统调用
> 语法: sendfile on|off;  
> 配置块: http、server、location

- AIO系统调用
> 语法: aio on|off;  
> 配置块: http, server, location

- directio(linux系统以O_DIRECT方式只读文件,缓冲区大小)
> 语法: directio size|off;  
> 配置块: http, server, location

- directio方式读取文件时的对齐方式
> 语法: directio_alignment size;  
> 配置块: http, server, location

- 打开缓存功能
> 语法: open_file_cache max=N[inactive=time]|off;  
> 配置块: http, server, location

- 是否缓存打开文件错误信息
> 语法: open_file_cache_errors on|off;  
> 配置块: http, server, location

- 不被淘汰的最小次数
> 语法: open_file_cache_min_users number;  
> 配置块: http, server, location

- 检验缓存中元素有效性的频率
> 语法: open_file_cache_valid time;  
> 配置块: http, server, location


## 对客户端请求的特殊处理
- 忽略不合法的HTTP头部
> 语法: ignore_invalid_headers on|off;  
> 配置块: http, server

- HTTP头部是否允许下划线
> 语法: underscores_in_headers on|off;  
> 配置块: http, server, location

- 对If-Modified-Since头部的策略处理
> 语法: if_modified_since [off|exact|before];  
> 配置块: http, server, location

- 文件未找到时是否记录到error日志
> 语法: log_not_fount off|on;  
> 配置块: http, server, location

- 是否匹配相邻的'/'
> 语法: merge_slashes on|off;  
> 配置块: http, server, location

- DNS解析地址
> 语法: resolver address ...;  
> 配置块: http, server, location

- DNS解析地址超时时间
> 语法: resolver_timeout time;  
> 配置块: http, server, location

- 返回错误页面时,是否在Server中注明nginx版本
> 语法: server_tokens on|off;  
> 配置块: http, server, location

## ngx_http_core_module模块提供的变量
![访问上游服务器时可使用的变量](/image/访问上游服务器时可使用的变量.png)

## 反向代理服务器的基本原理
基本原来的流程图如下：

![反向代理服务器转发请求流程](/image/反向代理服务器转发请求流程.png)

## 负载均衡的基本配置
- upstream块
> 语法: upstream name {...};  
> 配置块: http  

- server  
> 语法: server name [parameters];  
> 配置块: upstream

- ip_hash
> 语法: ip_hash;  
> 配置块: upstream

- 样例:
```nginx
upstream tianshenjr {  

    #ip_hash; 说明:与weight不可共存;

    server dev.tianshenjr.com weight=4;  
    server 127.0.0.1:8080 max_fails=3 fail_timeout=30s;  
    server unix:/tmp/api.tianshenjr.com;  
}  
server {  
    location / {  
        proxy_pass http://www.tianshenjr.com  
    }  
}
```

- 记录日志时支持的变量


## 反向代理的基本配置

- proxy_pass
> 语法: proxy_pass URL;  
> 配置块: location, if

- proxy_method
> 语法: proxy_method method;  
> 配置块: http, server, location

- proxy_hide_header
> 语法: proxy_hide_header the_header;  
> 配置块: http, server, location

- proxy_pass_header
> 语法: proxy_pass_header the_header;  
> 配置块: http, server, location

- proxy_pass_request_body
> 语法: proxy_pass_request_body on|off;  
> 配置块: http, server, location

- proxy_pass_request_headers
> 语法: proxy_pass_request_headers on|off;  
> 配置块: http, server, location

- proxy_redirect
> 语法: proxy_redirect [default|off|redirect replacement];  
> 配置块: http, server, location

- proxy_next_upstream
> 语法: proxy_next_upstream [error|timeout|invalid_header|http_500|http_502|http_503|http_504|http_404|off];
> 配置块: http, server, location

扩展阅读
   http://wiki.nginx.org/Modules


# 开发HTTP模块
## 如何调用HTTP模块
![http模块调用简化流程](/image/nginx http模块调用简化流程.png)

## 类型封装
- 整型
```C
typedef intptr_t ngx_int_t;
typedef uintptr_t ngx_uint_t;
```

- ngx_str_t 数据结构
```C
typedef struct{
    size_t      len;
    u_char      *data;
} ngx_str_t;
```

- ngx_list_t 数据结构
```C
typedef struct ngx_list_part_s ngx_list_part_t;

struct ngx_list _part_s{
    void                *elts;
    ngx_uint_t          nelts;
    ngx_list_part_t     *next;
};

typedef struct{
    ngx_list_part_t     *last;
    ngx_list_part_t     part;
    size_t              size;
    ngx_unit_t          nalloc;
    ngx_pool_t          *pool;
} ngx_list_t;
```
- ngx_table_elt_t 数据结构
- ngx_buf_t 数据结构
- ngx_chain_t 数据结构

## 准备工作
- 模块命名:  
按规范命名第一个模块的名字: ngx_http_mytest_module

- 文件命令:
源码一般使用C开发（或C++）,该模块命名为: ngx_http_mytest_module.c

- configure脚本执行时的ngx_addon_name变量的名称：ngx_http_mytest_module

