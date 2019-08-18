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

#### px

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

#### service vsftpd restart
重启vsftpd

## deamon

## LAMPP
start    开启所有(apache,mysql,ftp等)

## ffmpeg
音视频转码工具

#### 视频转换为ogg(需安装编码库)
ffmpeg -i 源文件 -acodec libvorbis 目标文件









