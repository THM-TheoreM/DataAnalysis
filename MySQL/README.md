﻿# MySQL

## 安装

- [官网](http://www.mysql.com)

- [安装教程](http://jingyan.baidu.com/article/597035521d5de28fc00740e6.html)

- [其他说明](http://bobshute.iteye.com/blog/520760)

## 教程

- [菜鸟教程](http://www.runoob.com/mysql/mysql-tutorial.html)

### 管理/链接

```
进入/启动：mysql -u root -p

退出：mysql> exit;
```

### 数据库

```
创建：mysqladmin -u root -p create RUNOOB

删除：mysqladmin -u root -p drop RUNOOB

选择：mysql -u root -p

      mysql> use RUNOOB;
```

### 数据类型

MySQL主要有三种数据类型：数值，日期和时间，以及字符串。对于`null`，要用`is null`和`is not null`来判断

### 函数

- 内建函数
  - count
  - sum
  - avg
  - max
  - min 

### 数据表

```
创建：create table runoob_tb(
      id int not null auto_increment,
      title varchar(100) not null,
      author varchar(40) not null,
      date date,
      primary key (id)
      );

       create table runoob_tb2(
       title varchar(100) not null,
       author varchar(40) not null,
       );       

删除：drop table runoob_tb;
```

### 插入

```
插入：insert into runoob_tb (title,author,date) values ("PHP","John Poul",NOW());
      insert into runoob_tb (title,author,date) values ("MySQL","Abdul S",NOW());
      insert into runoob_tb (title,author,date) values ("JAVA","Sanjay","2007-05-06");
      insert into runoob_tb (title,author,date) values ("HTML","gaoxinge","2016-07-24"), ("C++","xinge","2016-07-24"), ("Python","ge","2016-07-23");
      insert into runoob_tb2 select title,author from runoob_tb;
```

### 更新

```
更新：update runoob_tb set title="HTML" where id=4;
```

### 删除

```
删除：delete from runoob_tb where id=4;
```

### 查询

```
查询：select id from runoob_tb;
      select * from runoob_tb;
      select * from runoob_tb where id>1 and date!="2007-05-06";
      select * from runoob_tb where author like "%jay";
      select * from runoob_tb where author regexp "jay";
      select * from runoob_tb order by date;
      select date,count(*) from runoob_tb group by date;
      select a.id,a.author,b.count from runoob_tb a inner join tcount_tb b on a.author=b.author;
      select a.id,a.author,b.count from runoob_tb a left join tcount_tb b on a.author=b.author;
      select b.id,b.author,a.count from tcount_tb a right join runoob_tb b on a.author=b.author;
```

### 字段

```
字段：show columns from runoob_tb2;

添加：alter table runoob_tb2 add id int;

删除：alter table runoob_tb2 drop id;

修改：alter table runoob_tb2 modify id char(10);
      alter table runoob_tb2 change id ide char(10);
      alter table runoob_tb2 modify ide bigint not null default 100;
      alter table runoob_tb2 alter ide set default 1000;
      alter table runoob_tb2 alter ide drop default;

表名：alter table runoob_tb2 rename to tcount_tb;
```

### 索引

索引主要分为一般索引，唯一索引以及主键。他们都可由`create`创建，`alter`修改

## 其他

- [java](http://blog.sina.com.cn/s/blog_4d8648910102vagq.html)

- [python](http://www.runoob.com/python/python-mysql.html)

- [excel](http://blog.sina.com.cn/s/blog_731d4f750102uxpw.html)