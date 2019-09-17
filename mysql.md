## 配置



## mysqldump

#### mysqldump --opt 数据库名 > 文件名.sql
将数据库备份到一个sql文件

## mysql

#### mysql 数据库名 < 文件名.sql
在数据库上运行sql文件

#### mysql -u 用户名 -p
进入mysql终端

## mysqld
#### mysqld
启动mysql服务

#### mysqld stop
停止mysql服务

#### mysqld restart
重启mysql服务

## mysql终端命令

#### flush privileges
更新mysql.user表到mysql设置

#### show databases
显示数据库列表

#### use 数据库名
应用数据库

#### show tables
显示表列表

#### create database 数据库名
创建数据库

## 其他

#### 配置文件位置
使用````mysql --help````命令可查看配置文件的位置。默认如下：
* /etc/mysql/my.cnf

## 安装
#### linux二进制版
0. 安装前置：libnuma,libaio
1. 下载软件包并解压。如：````mysql-8.0.17-linux-glibc2.12-x86_64.tar.xz````
2. 添加使用的用户和用户组。````groupadd mysql````,````useradd -g mysql mysql````
3. 改变目录所有者为mysql用户。````chown -R mysql .````
4. 复制文件,````cp ./lib/libssl.so.1.0.0  ./bin````,````cp ./lib/libcrypto.so.1.0.0  ./bin````
5. 初始化，````./bin/mysqld --initialize --user=mysql````。**注意：要记好初始密码**
6. 配置配置文件。
7. 启动服务。````./bin/mysqld````









