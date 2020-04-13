## 数据库基础

### 一、基本概念

1.数据库管理系统：DBMS

2.数据库（DB）：保存了一个或一组文件，保存了一些符合特定规格的数据，英文名称DataBase，简称DB，数据库软件称为数据库管理系统，英文简称DBMS。

SQL：结构化查询语言

MySQL常用命令 
1. mysql -uroot  -p
2. mysql --version / mysql -V

show tables

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200408081929.png)

show databases

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200408081836.png)

select database();

创建数据库 create database + 数据库名称

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200408081702.png)

DQL 语句：数据查询语言 select

DML语句：数据操作语言 insert delete update

DDL语句：数据库定义语言 create drop alter

TCL语句：事务控制语言 commit rollback

desc 显示详细信息

select keyword form table；  查询语句

 查询多个字段用分号隔开

查询全部： select * from table；

select test*12 from table；

字段可以进行算术运算

select test*12  as 别名 from table；

as可以省略

3.条件查询：where 语句，where必须放在from语句表的后面

支持的运算符：

算术运算符：

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200408093143.png)

比较运算符：

![](https://markdownimages.oss-cn-beijing.aliyuncs.com/img/20200408093235.png)

select  name，sal form tables where sal = 5000；

单引号是标准写法

通配符 %

占位符 __

4.排序

order by 默认升序

esc desc
