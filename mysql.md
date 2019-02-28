## 配置文件
## mysqldump
#### mysqldump --opt 数据库名 > 文件名.sql
将数据库备份到一个sql文件
## mysql
#### mysql 数据库名<文件名.sql
在数据库上运行sql文件
#### mysql -u 用户名 -p 密码
进入mysql终端
## mysql终端命令
#### flush privieges
更新user表到mysql设置
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
* 全局 /etc/mysql
* 局部 ./etc/mysql











