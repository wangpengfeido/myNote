## nginx.conf
````
http{    # 协议级别块
    server{    # 服务级别块。它会创建一个虚拟主机
        listen 80;    # 端口号

        server_name www.trenfash.cn;    # 虚拟主机名称

        location uri {    # 请求级别块
            root;    # 资源路径（搜索时不带location uri）

            alias;    # 资源路径(搜索时带location uri)
            
            proxy_pass http://127.0.0.1:8080;    # 代理到的地址

            try_files ...请求路径 uri    # 尝试读取文件，读不到时进行内部重定向
            try_files ...请求路径 =返回码    # 读不到文件时返回返回码

            error_page ...错误码 uri    # 在错误时访问链接

            fastcgi_pass    # 代理到的cgi服务地址
        }
    }
}
````

### 变量
#### $uri
重写后的请求uri，不包含query
#### $request_uri
客户端发来的原生uri，包含query
#### $args
query参数
#### is_args
$args参数是否存在，存在则为"?"，不存在则为""



### location字段匹配规则
````location [=|~|~*|^~|@] pattern{……}````
#### 没有修饰符
必须以指定模式开始
#### =
必须与指定的模式精确匹配
#### ~
指定的正则表达式要区分大小写
#### ~*
指定的正则表达式不区分大小写
#### ^~
类似于无修饰符的行为，也是以指定模式开始，不同的是，如果模式匹配，
那么就停止搜索其他模式了。
#### @
定义命名location区段，这些区段客户段不能访问，只可以由内部产生的请
求来访问，如try_files或error_page等


## 命令
#### 启动
````nginx````
#### 重新载入配置
````nginx -s reload````
#### 从容停止
````nginx -s quit````
#### 立即停止
````nginx -s stop````


## 小注意
如果启动时报1113错误。原因是路径中有中文。

## ubuntu安装nginx
### apt-get安装方式
1. 安装前置
  * ````apt-get install zlib1g-dev````
  * ````apt-get install libpcre3 libpcre3-dev````
2. ````apt-get install nginx````

这种安装方式会自动创建服务，然后可以使用后面的命令````sudo service nginx {start|stop|restart|reload|force-reload|status|configtest|rotate|upgrade}````

### 手动编译方式
1. 安装前置：zlib、pcre、openssl
2. 下载软件包并解压
3. ````./configgure --prefix=安装路径````
4. ````make````,````make install````





