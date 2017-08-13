## 总览
#####  配置文件
配置文件书写格式：key = value。
* **port** 端口号
* **dbpath** 数据库文件的存放位置（文件夹）
* **logpath** 日志文件的存放位置（文件）
## mongod
##### 普通选项
###### -f 配置文件地址
指定配置文件
## mongo
mongo [options] [db address] [file names(ending in .js)]
##### db address 数据库地址
* **数据库名** 当数据库为本机时使用
* **ip:数据库名**
* **ip:端口号/数据库名**
##### 权限选项
###### -u [--username] 用户名
###### -p [--password] 密码
## 系统命令
###### show dbs
查看系统中的数据库。
###### use 数据库名
切换数据库，如果不存在该数据库则自动创建。
###### show collections
查看当前数据库中的集合。
###### show tables
查看当前数据库中的表。
###增删改查
###### db.shutdownServer()
关闭mongodb服务。
###### db.dropDatabase()
删除当前数据库。
###### db.集合名.insert(data)
向集合中插入数据。如果集合不存在则创建集合。

在插入的数据中，_id不能重复。
###### db.集合名.find(查询条件)
查找集合中的数据。
###### db.集合名.findOne()
查找集合中的第一条数据
###### db.集合名.count()
查询集合中数据条数
###### data.count()
查询数据条数
###### data.skip(n)
跳过n跳数据
###### data.limit(n)
最多查询n条数据
###### data.sort(keys)
排序数据
###### db.集合名.update(查询条件,data[,insertIfNotExist[,multiUpdate]])
更新数据
* **insertIfNotExist** Boolean Default:false 如果为true，则当查询的数据不存在时自动插入数据。如果更新的data中未使用$set操作符，则新插入的数据为更新的data；如果更新的data中使用了$set操作符，则新插入的数据为查询条件和更新的data的合体。
* **multiUpdate** Bollean Default:false 如果为false，则只更新首条查找到的数据；如果为true，更新所有查找到的数据，为true时更新的data中必须使用$set操作符

**$set**:部分更新操作符
###### db.集合名.remove(查询条件)
删除数据
###### db.集合名.drop()
删除集合
### 索引
###### db.集合名.getIndexes()
查询当前集合的索引
###### db.集合名.createIndex(keys[,options])
创建索引
* **keys**: 可以用{x:1}的格式创建单键索引和多键索引；用{x:1,y:1}的格式创建复合索引
* **options.expireAfterSeconds**:设置索引的过期时间,索引过期后，会将数据库中的数据删除。NOTE:*1.索引字段必须为时间类型；2.索引字段如果是时间数组，则按照最小时间进行删除；3.过期索引不能是复合索引；4.删除时间不是精确的*





