## 语法
### php标签    
#### <?php php标签 ?>    
php可嵌套在html中。

若为纯php文本，则标签末尾的?>可省略。

### 包含
#### include 'php文件路径';
#### include_once 'php文件路径'; 

### 依赖
#### require 'php文件路径';
include与require相近，但require错误提示级别更高。
#### require_once 'php文件路径';
require_once只引用一次，避免重复引用。

### 变量
#### $变量名=值;
访问变量也为$变量名。
#### 字符串
字符串连接使用“.”。

字符串可用单引号，也可用双引号。

字符串使用双引号时，可在引号内直接使用变量。
#### 数组
* ````$数组=array([下标/'键'=>值,...]/[值,...]);````
* ````$数组['键'/0]=值;...````
* 键值对存放值 ````$数组变量名['键']=值;...````
* 嵌套数组 ````$数组变量名=array(array());````

### 常量
#### const 常量名=值;
const只适用于php5以上。php5一下用下面的语句。
#### define(“常量名”：,值);

### switch
switch内容可为小数。

### 循环    
#### for(;;){}
#### while(){}
#### do{}while();

### 逻辑
#### &&
#### ||
#### ==
#### !=
#### <
#### >

### 函数
#### function 函数名(参数列表){ [return x;] }
#### 函数变量
````$变量名=”函数名”;$变量名();````

### 类
#### 定义类
````class 类名{权限修饰符 属性/方法定义;}````
#### 定义对象
````$对象名=new 类名(参数列表);````
#### 访问类成员
````$对象名->成员````
#### 构造方法
````__construct(参数列表){}````
#### ````$this->成员;````
#### 静态变量
* 定义 ````修饰符 static $变量名=值;````
* 访问 ````类名::$静态变量名````
####  静态常量 
* 定义````const 常量名=值;````
* 访问 ````类名::$静态常量名````
#### 静态方法
* 定义 ````修饰符 static 方法定义````
* 访问 ````类名::方法名();````

### 类的继承
#### ````class 类名 extends 父类名{}````
在继承之前需将父类文件引用。
#### 调用父类方法
````parent::方法名(参数列表);````

### 命名空间
* 定义 ````namespace 命名空间名;````
* *使用 `````\命名空间名\类名;`````

### 输出
* echo 值;
* 输出数组 ````print_r(数组);````

### header    
#### ````header(报头字符串[,是否替换之前报头,强制指定值])```` 
发送http报头。
* 参数一：Content-type:mime type（发送mime type报头）；Location:地址(跳转)。

### die
````did('字符串');````

结束程序运行并输出字符串。

### 值类型转换
````intval();````

### 查看变量是否定义
````isset();````

### 查看变量是否为空
````empty();`````

### 字符串操作
* ````strpos(字符串,子串);```` 查找字串的位置
* ````substr(字符串,数[,数]);```` 截取字符串，如没有第三个参数则截取到末尾
* ````str_split(字符串[,数])```` 按数分割字符串，默认为1。返回字符串数组。
* ````explod(分隔符,字符串);```` 按分隔符分割字符串。返回字符串数组。
### 数组操作
* ````array_push(数组变量,”值”);```` 向数组添加值。
* ````array_splice(数组变量,开始下标,个数)```` 删除元素并重新排列索引
	     
### 表单
* ````$_GET[]```` 获取get方式传入的值    注：数组的key为传入值的key。
* ````$_POST[]```` 获取post方式传入的值
* ````$_FILE[]```` 获取传入的文件。注：数组的每个元素还是一个数组，其中的key有,name（名称）,type（mime type）,tmp_nmae(暂存目录),err,size。

### Cookie
* ````setcookie('key','value');```` 设置cookie键值对。
* ````$_COOKIE[]```` 获取cookie数组。注：当cookie被禁用时，可用get方式在页面之间传递数据。

### Session
* ````session_start();```` 开始一个特定的session。
* ````$_SESSION[];```` 设置或获取session。
* ````session_id();```` 获取当前特定session的id。
* ````session_destroy();```` 销毁当前特定session。

### 时间
* ````time();```` 获取时间戳，从1970开始计算的毫秒数。
* ````date('格式参数'[,'时间戳']);```` 获取（当前/时间戳转换）日期
* ````date_default_timezone_get();```` 获取时区
* ````date_default_timezone_set('参数');````  设置时区    注：参数可在帮助中查找。

### Json
* ````json_encode(数组);```` 将数组转换为JSON字符串。注：有键值对数组将生成JSON对象。  
* ````json_decode();```` 将JSON字符串转换为数组或对象。

### 文件读写
* ````fopen('文件名','打开模式')```` 打开文件，返回文件标识。
* ````fwrite(文件标识,'数据');```` 写文件。注：若要写入换行使用\r\n，并且要用双引号。
* ````fgets(文件标识);```` 读文件。注：只读取一行数据。
* ````fclose(文件标识);```` 关闭文件。

### 文件操作
* ````move_uploaded_file(待移动目录,移动到目录);``` 将加载的文件移动到指定目录。

### 图片(GD)
* ````imagecreate(宽,高);```` 创建图片，返回图片资源。
* ````imagecreatefromjpeg('文件名');```` 从已有jpg文件创建图片。
* ````imagecolorallocate(图片资源,红,绿,蓝);```` 为图片创建背景色，返回颜色变量。    注：只能设置一次背景色。
* ````imageellipse(图片资源,中心x,中心y,宽,高,颜色);```` 绘制椭圆。
* ````imagestring(图片资源,字体,位置x,位置y,颜色);```` 添加文字。
* ````imagecopymerege(目的图片,加入图片,目的图x,目的图y,加入图x,加入图y,宽,高,透明度);````
* ````imagepng(图片资源);```` 以png格式输出图片。注：向浏览器发送前要使用header()发送文件头，见输出部分。

### mysqp数据库
* ````mysql_connect('数据库服务器地址','用户名','密码');```` 链接到数据库服务器。成功返回服务器标识;失败返回false。
* ````mysql_select_db('数据库名'[,服务器标识]);```` 链接到数据库
* ````mysql_query('sql语句'[,服务器标识]);```` 执行sql语句，返回结果。注：数据库防注入攻击，字符串一定要用引号引起，数值一定提前做类型转换。
* ````mysql_fetch_arry(查询结果);```` 将查询结果转换为数组。数组中包含数字索引和key索引。注：转换是转换一条记录，第二次转换下一条记录。
* ````mysql_fetch_assoc(查询结果);```` 将查询结果转换为数组。数组中只包含key索引。
* ````mysql_num_rows(查询结果);```` 返回查询结果的条数。
* ````mysql_error();```` 返回错误数量。
* ````mysql_error();```` 返回错误信息。

## linux 安装方式
### 安装
1. 安装依赖：libxml2
2. 下载安装包后解压
3. ````./configure --prefix=xxx --enable-fpm --with-pdo-mysql````
4. 错误：
  * recipe for target ‘ext/phar/phar.php’ failed.make: *** [ext/phar/phar.php] Error 127.解决：进入/php/ext/phar文件夹，运行````cp ./phar.php  ./phar.phar````
5. ````make````,````make test````,````make install````

### config参数
#### --prefix=
配置安装路径
#### --enable-fpm
包含php-fpm扩展
#### --with-mysql（7.0之前）/--with-pdo-mysql（7.0之后）
包含mysql库

### 配置php/

### php-fpm
#### 配置 php/etc/php-fpm.d/www.conf
````
user = www-data    # 设置启动使用的用户
group = www-data    # 设置启动使用的用户组
listen = /tmp/php-fpm.sock   # 设置php监听。nginx中的fastcgi_pass选项应该与之一致。也可设置成ip:port，如127.0.0.1:9000 
listen.mode = 0666    # 监听模式
````
#### 配置 php/etc/php-fom.conf

#### php-fpm命令
* 启动 ````php/sbin/php-fpm````
* 重启、终止。使用kill命令，附加INT（终止）、USR2（重启）等信号
































