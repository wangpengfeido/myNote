



## nginx.conf
````
http{
    server{

        # 端口号
        listen 80

        # 虚拟主机名称。即反向代理时转发到的地址
        server_name www.trenfash.cn

        location uri {
            # 代理到的地址
            proxy_pass http://127.0.0.1:8080
        }
    }
}
````


## 小注意
如果启动时报1113错误。原因是路径中有中文。

## ubuntu安装nginx
apt-get install nginx

安装好的文件位置：
* 主程序：/user/sbin/nginx
* 静态文件：/etc/nginx
* 日志：/var/log/nginx

这种安装方式会自动创建服务，然后可以使用后面的命令````sudo service nginx {start|stop|restart|reload|force-reload|status|configtest|rotate|upgrade}````






