## 命令
#### ./
运行当前目录下的可执行文件

#### sudo
以管理员身份运行

参数：
* su 将控制台切换到root权限

#### gksudo
以管理员身份运行图形界面程序

#### cd
切换控制台工作路径

参数：
* ..  返回上级目录
* /  至根目录

#### ls
ls 命令将每个由 Directory 参数指定的目录或者每个由 File 参数指定的名称写到标准输出，以及您所要求的和标志一起的其它信息。如果不指定 File 或 Directory 参数， ls 命令显示当前目录的内容。

参数：
* -a 列出目录下的一切文件，包含以 . 最初的隐含文件。//常用 　
* -m 横向输出文件名，并以“，”作分格符。
* -c 输出文件的 i 节点的修正时刻，并以此排序。
* -R 列出一切子目录下的文件。
* -l 列出文件的具体信息。
* -s 在每个文件名后输出该文件的巨细。
* -k 以 k 字节的方式表明文件的巨细。
* -i 输出文件的 i 节点的索引信息。

#### chmod
改变文件或目录的访问权限

chmod [who] [opt] [mode] 文件/目录名

who：
* u：表示文件所有者 
* g：表示同组用户 
* o：表示其它用户 
* a：表示所有用户 

opt： 
* +：添加某个权限 
* -：取消某个权限 
* =：赋予给定的权限，并取消原有的权限 
* -R:操作传递给子文件、文件夹

mode： 
* r：可读 =4
* w：可写 =2
* x：可执行 =1
* 注：可将几个数字相加。

#### mkdir
建立新目录

mkdir [-p] dirName

参数：
* -p 确保目录名称存在，如果目录不存在的就新创建一个。

#### rm
移除文件或文件夹

参数：
* -r    将参数中列出的全部目录和子目录递归删除
* -f    忽略不存在的文件
* -i    进行交互式删除
* -v    显示进行的步骤

#### mv
移动文件或文件夹

move [参数] 源路径 目标路径

参数：
* -b：若需覆盖文件，则覆盖前先行备份。
* -f：force强制的意思，如果目标文件已经存在，不会询问而直接覆盖；
* -i：若目标文件(destination)已经存在时，就会询问是否覆盖！
* -u：若目标文件已经存在，且source比较新，才会更新(update)
* -t ：--target-directory=DIRECTORY move all SOURCE arguments into DIRECTORY，即指定mv的目标目录，该选项适用于移动多个源文件到一个目录的情况，此时目标目录在前，源文件在后。

#### cp
复制文件或文件夹

参数：
* -r    递归处理，将指定目录下的所有文件与子目录一并处理
* -f    强行复制文件或目录，不论目标文件或目录是否已存在

#### touch
修改文件或目录的时间属性，如果文件不存在，则会创建一个新文件。
````
touch [-acfm][-d<日期时间>][-r<参考文件或目录>] [-t<日期时间>][--help][--version][文件或目录…]
````

#### cat
连接文件并打印到标准输出设备

cat [-AbeEnstTuv] [--help] [--version] fileName

参数：
* -n 或 --number：由 1 开始对所有输出的行数编号。
* -b 或 --number-nonblank：和 -n 相似，只不过对于空白行不编号。
* -s 或 --squeeze-blank：当遇到有连续两行以上的空白行，就代换为一行的空白行。
* -v 或 --show-nonprinting：使用 ^ 和 M- 符号，除了 LFD 和 TAB 之外。
* -E 或 --show-ends : 在每行结束处显示 $。
* -T 或 --show-tabs: 将 TAB 字符显示为 ^I。
* -A, --show-all：等价于 -vET。
* -e：等价于"-vE"选项；
* -t：等价于"-vT"选项；

#### ps
查看当前进程

参数：
* -A ：所有的进程均显示出来，与 -e 具有同样的效用。
* -a ： 显示现行终端机下的所有进程，包括其他用户的进程。
* -u ：以用户为主的进程状态。
* x ：通常与 a 这个参数一起使用，可列出较完整信息。

输出格式规划：
* l ：较长、较详细的将该PID 的的信息列出。
* j ：工作的格式 (jobs format)。
* -f ：做一个更为完整的输出。

例如：
* ````ps aux```` 显示所有内存当中的进程
* ````ps aux|grep java````与grep命令一起使用，查找名字里带有java的进程

#### kill
中止一个进程

kill [options] <pid> [...]

参数：
* -s：指定发送的信号。
* -p：模拟发送信号。
* -l：指定信号的名称列表。
* -\<signal\> : 指定发送给进程的信号，指定信号的名称或号码都可以。
* pid: 进程号

信号：
* -INT 快速关闭。中止当前操作
* -QUIT 平滑中止
* -USR2 平滑升级
* -HUP 平滑重启

#### grep
查找文件里符合条件的字符串

grep [-abcEFGhHilLnqrsvVwxy][-A<显示行数>][-B<显示列数>][-C<显示列数>][-d<进行动作>][-e<范本样式>][-f<范本文件>][--help][范本样式][文件或目录...]

参数：
* -a 或 --text : 不要忽略二进制的数据。
* -A<显示行数> 或 --after-context=<显示行数> : 除了显示符合范本样式的那一列之外，并显示该行之后的内容。
* -b 或 --byte-offset : 在显示符合样式的那一行之前，标示出该行第一个字符的编号。
* -B<显示行数> 或 --before-context=<显示行数> : 除了显示符合样式的那一行之外，并显示该行之前的内容。
* -c 或 --count : 计算符合样式的列数。
* -C<显示行数> 或 --context=<显示行数>或-<显示行数> : 除了显示符合样式的那一行之外，并显示该行之前后的内容。
* -d <动作> 或 --directories=<动作> : 当指定要查找的是目录而非文件时，必须使用这项参数，否则grep指令将回报信息并停止动作。
* -e<范本样式> 或 --regexp=<范本样式> : 指定字符串做为查找文件内容的样式。
* -E 或 --extended-regexp : 将样式为延伸的普通表示法来使用。
* -f<规则文件> 或 --file=<规则文件> : 指定规则文件，其内容含有一个或多个规则样式，让grep查找符合规则条件的文件内容，格式为每行一个规则样式。
* -F 或 --fixed-regexp : 将样式视为固定字符串的列表。
* -G 或 --basic-regexp : 将样式视为普通的表示法来使用。
* -h 或 --no-filename : 在显示符合样式的那一行之前，不标示该行所属的文件名称。
* -H 或 --with-filename : 在显示符合样式的那一行之前，表示该行所属的文件名称。
* -i 或 --ignore-case : 忽略字符大小写的差别。
* -l 或 --file-with-matches : 列出文件内容符合指定的样式的文件名称。
* -L 或 --files-without-match : 列出文件内容不符合指定的样式的文件名称。
* -n 或 --line-number : 在显示符合样式的那一行之前，标示出该行的列数编号。
* -o 或 --only-matching : 只显示匹配PATTERN 部分。
* -q 或 --quiet或--silent : 不显示任何信息。
* -r 或 --recursive : 此参数的效果和指定"-d recurse"参数相同。
* -s 或 --no-messages : 不显示错误信息。
* -v 或 --revert-match : 显示不包含匹配文本的所有行。
* -V 或 --version : 显示版本信息。
* -w 或 --word-regexp : 只显示全字符合的列。
* -x --line-regexp : 只显示全列符合的列。
* -y : 此参数的效果和指定"-i"参数相同。

#### tar
解压tar包

主选项：
* c 创建新的档案文件。如果用户想备份一个目录或是一些文件，就要选择这个选项。相当于打包。
* x 从档案文件中释放文件。相当于拆包。
* t 列出档案文件的内容，查看已经备份了哪些文件。

辅助选项：
* z ：是否同时具有 gzip 的属性？亦即是否需要用 gzip 压缩或解压？ 一般格式为xx.tar.gz或xx. tgz
* j ：是否同时具有 bzip2 的属性？亦即是否需要用 bzip2 压缩或解压？一般格式为xx.tar.bz2  
* v ：压缩的过程中显示文件。这个常用
* f ：使用档名，请留意，在 f 之后要立即接档名。不要再加其他参数！
* p ：使用原文件的原来属性（属性不会依据使用者而变）

#### dpkg
debian软件包管理

* dpkg -i 文件名    安装deb软件包
* dpkg -r 包名    删除软件包
* dpkg -P 包名    清除软件包（包括配置信息）
* dpkg -l [包名]    查看安装的软件包

#### curl

#### bash
Bourne Shell 的扩展。

#### chown
改变文件的拥有者
````
chown [-cfhvR] [--help] [--version] user[:group] file...
````
参数:
* user : 新的文件拥有者的使用者 ID
* group : 新的文件拥有者的使用者组(group)
* -c : 显示更改的部分的信息
* -f : 忽略错误信息
* -h :修复符号链接
* -v : 显示详细的处理信息
* -R : 处理指定目录以及其子目录下的所有文件
* --help : 显示辅助说明
* --version : 显示版本

#### groups
查看当前用户/某用户所属的用户组。
````
groups [选项] [用户名]
````
选项：
* -help 显示命令的帮助信息；
* --version 显示命令的版本信息。

#### groupadd
添加用户组
````
groupadd [选项] 用户组名
````
选项：
* -g：指定新建工作组的id；
* -r：创建系统工作组，系统工作组的组ID小于500；
* -K：覆盖配置文件“/ect/login.defs”；
* -o：允许添加组ID号不唯一的工作组。

#### adduser
添加用户
````
adduser [-c comment] [-d home_dir] [-e expire_date] [-f inactive_time] [-g initial_group] [-G group[,...]] [-m [-k skeleton_dir] | -M] [-p passwd] [-s shell] [-u uid [ -o]] [-n] [-r] loginid
````
选项：
* -c \<备注\>：加上备注文字。备注文字会保存在passwd的备注栏位中；
* -d \<登入目录\>：指定用户登入时的启始目录；
* -D：变更预设值；
* -e \<有效期限\>：指定帐号的有效期限；
* -f \<缓冲天数\>：指定在密码过期后多少天即关闭该帐号；
* -g \<群组\>：指定用户所属的群组；
* -G \<群组\>：指定用户所属的附加群组；
* -m：自动建立用户的登入目录；
* -M：不要自动建立用户的登入目录；
* -n：取消建立以用户名称为名的群组；
* -r：建立系统帐号；
* -s \<shell\>：指定用户登入后所使用的shell；
* -u \<uid\>：指定用户id。

#### passwd
更改用户密码。
````
passwd [-k] [-l] [-u [-f]] [-d] [-S] [username]
````

#### ln
为一个文件在另一个位置建立同步链接
````
[-bdfinsvF] [-S backup-suffix] [-V {numbered,existing,simple}]
[--help] [--version] [--]
````
选项：
* -s 软链接(符号链接)



## 文件

#### /etc/passwd
存储用户列表

#### /etc/group
存储用户组列表

#### /etc/init.d/
自启动脚本目录

#### /usr/local/
存储安装的系统级应用程序。它是make命令的默认目录。

#### /opt/
存放安装的应用程序

#### .d后缀文件夹
由程序开发者创建，存放配置文件。

## 技巧

# 常用程序

## apt-get
自动从互联网的软件仓库中搜索、安装、升级、卸载软件或操作系统。

apt-get [选项] 命令 [软件包名]

命令：
* update 获取取软件包列表 在修改/etc/apt/sources.list或/etc/apt/preferences之后运行该命令。此外您需要定期运行这一命令以确保您的软件包列表是最新的。
* install 安装
* remove 移除
* autoremove 自动移除软件包和配置文件
* upgrade 更新指定软件包
* source 下载软件包源码
* check 检验依赖是否有损坏

#### apt-get install packagename
安装一个新软件包

#### apt-get remove packagename
卸载一个已安装的软件包（保留配置文档）

#### apt-get purge packagename
卸载一个已安装的软件包（不保留配置文件）

#### apt-get autoremove
删掉所有不需要的依赖软件包

#### apt-get autoclean
删掉过期的deb安装包

#### apt-get clean
删掉所有deb安装包

## gedit
编辑文档

## nano
文本编辑工具

nano 文件名

## unzip

## VSFTPD

#### service vsftpd start
启动

#### service vsftpd restart
重启

#### service vsftpd status
查看状态

#### 参考配置
* 添加用户，例如
````
useradd uftp
passwd uftp
````
* /etc/vsftpd.conf
````
# 可写
write_enable=YES
# 登录用户配置
userlist_file=/etc/vsftpd.user_list
userlist_enable=YES
userlist_deny=NO
# 目录配置
local_root=/opt
````

## deamon

## LAMPP
start    开启所有(apache,mysql,ftp等)

## ffmpeg
音视频转码工具

#### 视频转换为ogg(需安装编码库)
ffmpeg -i 源文件 -acodec libvorbis 目标文件









