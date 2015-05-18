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
	create database xitongxue;
####1.2 删除数据库		
 	drop database xitongxue;
####1.3 使用数据库
 	use xitongxue;

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
	create table user;
####3.2 删除表	
 	drop table user;
####3.3 更新表名
 	rename table `xitongxue`.`user` TO `xitongxue`.`user_file`;
 ####3.4 添加字段
 	alter table `user` ADD `age` INT NOT NULL ;