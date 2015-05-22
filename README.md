# MySQL-快速入门
访问[php.xitongxue.com观看课程](http://xitongxue.com)
关注我们的ＱＱ群：390536187

##MySQL简介
MySQL是一种开放源代码的关系型数据库管理系统，目前属于 Oracle 公司
由于其体积小、速度快、总体拥有成本低，尤其是开放源码这一特点，一般中小型网站的开发都选择 MySQL 作为网站数据库。

##MYSQL安装与图形界面工具

####1.MYSQL安装教程请观看我们[PHP环境搭建课程](http://xitongxue.com/course/11)

####2.图形界面工具phpmyadmin
下载地址[http://www.phpmyadmin.net/home_page/downloads.php](http://www.phpmyadmin.net/home_page/downloads.php)
或者百度搜索phpmyadmin下载

下载完成后，解压并放到网站的根目录即可，最后访问http://localhost/phpmyadmin/index.php，进入管理界面。

##MYSQL语法

###1.创建你的第一个数据库

####1.1 创建数据库
	CREATE DATABASE xitongxue;
####1.2 删除数据库		
 	DROP DATABASE xitongxue;
####1.3 使用数据库
 	USE xitongxue;

###2.常用的数据类型
(1) int 整形　长度一般取10

(2) varchar　字符串　长度最大一般取255

(3) text　文本　

(4) float　单精度浮点　用法(10,2) 总长10位,保留到小数点后2位　有误差

(5) double　双精度浮点　用法(10,2) 总长10位,保留到小数点后2位　有误差

(6) decimal  小数　没有误差

(5) date　日期

(6) enum　枚举

###3.创建你的第一张表

####3.1 创建表

````
CREATE TABLE `user` (
  `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 AUTO_INCREMENT=1 ;
````
####3.2 删除表	

````
DROP TABLE `user`;
````
####3.3 更新表名

````
 RENAME TABLE `xitongxue`.`user` TO `xitongxue`.`user_file`;
````
####3.4 添加字段

````
 ALTER TABLE `user` ADD `age` INT NOT NULL ;
````

###4.插入数据

````
INSERT INTO `user` set  `age` = 1;
````

###5.删除数据

````
DELETE FROM `user` WHERE  1;
````

###6.更新数据

````
UPDATE `user` SET `age`=2 WHERE 1;
````

##查询
````
user 

id name age sex 
````
###1.语句格式
SELECT [ALL|DISTINCT] <目标列表达式>
                                                [，<目标列表达式>] …

FROM <表名或视图名>[， <表名或视图名> ] …

[ WHERE <条件表达式> ]

[ GROUP BY <列名1> [ HAVING <条件表达式> ] ]

[ ORDER BY <列名2> [ ASC|DESC ] ]；

###2. 单表查询

####2.1 查询指定列
[例]  查询全体用户的姓名与生日。

````
SELECT name，age
FROM user；
````
####2.2 查询全部列
[例]  查询全体用户的详细记录。

````
SELECT *
FROM user；
````
####2.3 查询经过计算的值

1.算术表达式
2.字符串常量
3.函数
4.列别名

````
SELECT name ，'Year of Birth: ’  BIRTH，
   2015-age，LOWER(sex)  
FROM user；
````

####2.4 取消取值重复的行

指定DISTINCT关键词，去掉表中重复的行 
 
````
SELECT DISTINCT age
FROM user； 
````

####2.5 常用的查询条件Where 子句

查询条件|谓词
:---------------|:---------------
比较|=，>，<，>=，<=，!=，<>；
确定集合|IN，NOT IN
字符匹配|LIKE，NOT LIKE
空    值|IS NULL，IS NOT NULL
多重条件（逻辑运算）|AND，OR，NOT

####2.6 ORDER BY子句

可以按一个或多个属性列排序
升序：ASC；降序：DESC；缺省值为升序

####2.7 聚集函数
计数
COUNT（[DISTINCT|ALL] *）
COUNT（[DISTINCT|ALL] <列名>）

计算总和
SUM（[DISTINCT|ALL] <列名>）	

计算平均值
AVG（[DISTINCT|ALL] <列名>）

最大最小值
MAX（[DISTINCT|ALL] <列名>）
MIN（[DISTINCT|ALL] <列名>）

####2.8 GROUP BY子句

HAVING短语作用于组，从中选择满足条件的组

区别：
WHERE子句中的条件表达式在分组之前起作用
而HAVING子句中的条件表达式在形成分组后起作用

###3. 多表连接查询

连接查询：同时涉及多个表的查询

````
SELECT user.name，course.title
FROM    user，course    /*多表连接*/
WHERE  course.userId = user.id 
   and user.age > 20 ；
````

