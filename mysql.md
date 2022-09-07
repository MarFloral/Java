[TOC]



# <!--注释-->

1. 本次学习使用的数据库为5.5.40
2. 【】内的内容表示可以不写
3. 所有的“……”表示以此类推 或任意个
4. 此表内的“约束”表示“约束条件”
5. 例如：【三：5：1）】的表示目录索引

# MySQL

## 	进入数据库

```cmd
mysql -uroot -p
```

## 		查看所有数据库

```mysql
show databases;
```

## 		一、数据库

### 				1、创建数据库

```mysql
create database 数据库名;
```

### 				2、删除数据库

```mysql
drop database 数据库名;
```

### 				3、选择数据库

```mysql
use 数据库名;
```

## 	二、数据类型

### 		1、数值类型

| ***整数类型***   | ***字节*** | ***范围（有符号）***                                    | ***范围（无符号）***            | ***描述***                                           |
| ---------------- | ---------- | ------------------------------------------------------- | ------------------------------- | ---------------------------------------------------- |
| tinyint          | 1字节      | (-128，127)                                             | (0，255)                        | 整型                                                 |
| smallint         | 2字节      | (-32 768，32 767)                                       | (0，65 535)                     | 整型                                                 |
| mediumint        | 3字节      | (-8 388 608，8 388 607)                                 | (0，65 535)                     | 整型                                                 |
| **int或integer** | **4字节**  | **(-2 147 483 648，2 147 483 647)**                     | **(0，4 294 967 295)**          | **整型**                                             |
| bigint           | 8字节      | (-9 233 372 036 854 775 808，9 223 372 036 854 775 807) | (0，18 446 744 073 709 551 615) | 整型                                                 |
| **float**        | **4字节**  | ****                                                    | ****                            | **单精度浮点数值**                                   |
| **double**       | **8字节**  | ****                                                    | ****                            | **双精度浮点数值**                                   |
| **decimal**      | ****       | ****                                                    | ****                            | **小数，用于精度要求非常高的计算中。（常用于货币）** |

### 		2、字符串类型

| ***字符串类型*** | ***字节大小***      | ***描述及存储需求***                              |
| ---------------- | ------------------- | ------------------------------------------------- |
| **char**         | **0-255字节**       | **定长字符串**                                    |
| **varchar**      | **0-255字节**       | **变长字符串**                                    |
| tinyblob         | 0-255字节           | 不超过 255 个字符的二进制字符串                   |
| tinytext         | 0-255字节           | 短文本字符串                                      |
| blob             | 0-65535字节         | 二进制形式的长文本数据                            |
| text             | 0-65535字节         | 长文本数据                                        |
| mediumblob       | 0-16777215字节      | 二进制形式的中等长度文本数据                      |
| mediumtext       | 0-16777215字节      | 中等长度文本数据                                  |
| logngblob        | 0-4294967295字节    | 二进制形式的极大文本数据                          |
| longtext         | 0-4 294 967 295字节 | 极大文本数据                                      |
| varbinary(m)     |                     | 允许长度0-M个字节的定长字节符串，值的长度+1个字节 |
| binary(m)        |                     | 允许长度0-M个字节的定长字节符串                   |

### 		3、日期和时间类型

| ***类型*** | ***大小(字节)*** | ***格式***          | ***用途***               |
| ---------- | ---------------- | ------------------- | ------------------------ |
| date       | 4                | YYYY-MM-DD          | 日期                     |
| time       | 3                | HH:MM:SS            | 时间                     |
| year       | 1                | YYYY                | 年份                     |
| datetime   | 8                | YYYY-MM-DD HH:MM:SS | 混合日期和时间值         |
| timestamo  | 4                | YYYYMMDD HHMMSS     | 混合日期和时间值，时间戳 |

## 		三、表

### 				1、查看数据库内的所有表

​		

```mysql
show tables 【from 数据库名】;
```



### 				2、创建表

```mysql
create table 表名(
    字段名1 数据类型 【约束】,
    字段名2 数据类型 【约束】,
    ……
    字段名n 数据类型 【约束】
);
```

### 				3、删除表

```mysql
drop table 表名;
```

### 		4、添加新字段

```mysql
alter table 表名 add 字段名 数据类型 【约束】;
```

### 		5、修改字段

<!--注：如果原字段拥有约束，不写约束时将改变该字段的约束-->

#### 					1）重命名

```mysql
alter table 表名 change 原字段名 新字段名 数据类型 【约束】;
```

#### 					2）非重命名

```mysql
alter table 表名 modify 字段名 数据长度 【约束】;
```

### 		6、删除字段

```mysql
alter table 表名 drop 字段1,drop 字段2,……；
```

## 	四、数据库的更新

### 		1、添加数据

```mysql
insert into 【(字段1,字段2……)】values(值1,值2,……);
```

<!--注：【】内不写时按创建表的字段顺序逐个添加值-->

### 		2、修改数据

```mysql
update 表名 set 字段1=值1,字段2=值2,
```

### 		3、删除数据

```mysql
delete from 表名 【where 条件】;
```

<!--注：【】内不加条件时将会把该表数据全部删除-->

## 	五、约束

### 		1、非空约束(not null) NK

创建表时：

```mysql
create table person(
    id int(5) not null,
    name varchar(10) default 0
);
```

创建表后：

```mysql
alter table person modify id int(5) not null;
```

<!--具体可见：【三：5】-->

### 		2、唯一约束(unique) UK

```mysql
create table person(
    id int(5) unique,
    name varchar(10),
    constraint uk_name unique(name)
);
```

### 		3、主键约束(primary key) PK

```mysql
create table person(
    id int(5) primary key,
    name varchar(10)
);

create table person(
    id int(5),
    name varchar(10),
    constraint pk_id primary key(id)
);
```

​	复合主键：

```mysql
create table person(
    id int(5),
    name varchar(10),
    constraint pk_id primary key(id，name)
);
```

### 		4、检查约束(check) CK

```mysql
#注：检查约束在旧版MySQL中不能被识别，但不会报错
create table person(
    id int(5) primary key,
    name varchar(10)，
    gender varchar(3),
    age int(3),
    constraint ck_gender check(gender in('男','女')),
    constraint ck_age check(age between 0 and 120)
);
```



### 		5、外键约束（foreign key）FK

```mysql
create table person(
    id int(5) primary key,
    name varchar(10)
);

create table person2(
    uid int(5),
    name varchar(10),
    constraint pk_uid primary key(uid)，
    constraint fk_uid foreign key(uid) references person(id)
);
```

#### 			1)级联删除（on delete cascade）

```mysql
create table person(
    id int(5) primary key,
    name varchar(10)
);

create table person2(
    uid int(5),
    name varchar(10),
    constraint pk_uid primary key(uid)，
    constraint fk_uid foreign key(uid) references person(id) on delete cascade
);
```



## 	六、数据库查询

测试前置准备：

```mysql
#创建表DEPT
create table dept(   
	deptno mediumint unsigned not null default 0,#部门编号
	dname varchar(20)  not null  default "",#部门名称
	loc varchar(13) not null default ""#位置
) engine=MyISAM default charset=utf8 ; 

#创建表EMP雇员
create table emp(
	empno  mediumint default 0,#员工编号
	ename varchar(20)  default "",#姓名
	job varchar(9) default "",#职位
	mgr mediumint,#领导编号
	hiredate date,#入职时间
	sal decimal(7,2),#工资
	comm decimal(7,2),#奖金
	deptno mediumint default 0#部门编号 
)engine=MyISAM default charset=utf8 ;

#工资级别表
create table salgrade(	
	grade mediumint UNSIGNED not null default 0,  
	losal decimal(17,2)  not null,  
	hisal decimal(17,2)  not null	
)ENGINE=MyISAM default charset=utf8;

#工资级别表  插入数据
insert into salgrade values (1,700,1200);
insert into salgrade values (2,1201,1400);
insert into salgrade values (3,1401,2000);
insert into salgrade values (4,2001,3000);
insert into salgrade values (5,3001,9999);

#员工表  插入数据
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno) 
values (7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800, null, 20);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600, 300, 30);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250, 500, 30);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975, null, 20);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250, 1400, 30);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850, null, 30);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, null, 10);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7788, 'SCOTT', 'ANALYST', 7566, '1987-04-19', 3000, null, 20);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7839, 'KING', 'PRESIDENT', null, '1981-11-17', 5000, null, 10);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500, 0, 30);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7876, 'ADAMS', 'CLERK', 7788, '1987-05-23', 1100, null, 20);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950, null, 30);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000, null, 20);
insert into EMP (empno, ename, job, mgr, hiredate, sal, comm, deptno)
values (7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300, null, 10);

#部门表  插入数据
insert into DEPT (deptno, dname, loc)
values (10, 'ACCOUNTING', 'NEW YORK');
insert into DEPT (deptno, dname, loc)
values (20, 'RESEARCH', 'DALLAS');
insert into DEPT (deptno, dname, loc)
values (30, 'SALES', 'CHICAGO');
insert into DEPT (deptno, dname, loc)
values (40, 'OPERATIONS', 'BOSTON');	
```

### 		1、简单查询

#### 			1）语法

```mysql
# distinct 消除重复值
select 【distinct】*|字段1 【别名】,字段2 【别名】,…… from 表名;
#例：
select * from emp;
```

#### 			2）实例：

1.  查询emp表中所有员工的编号，姓名，职位

    ```mysql
    select empno,ename,job from emp;
    #查询的时候可以指定查询的返回列的名称。 即为列起一个别名
    select empno eno,ename en,job j from emp;
    ```

2.  查询emp表中所有员工的职位

    ```mysql
    select job from emp;
    #消除重复列
    select distinct job from emp;
    ```

3.  查询emp表中每个员工的姓名和年薪

    ```mysql
    select ename,sal*12 from emp;
    ```

### 		2、限定查询（where）

#### 			1）语法

```mysql
select [distinct] * | 字段1 别名，字段2 别名...  from 表名
[where 条件]
#在where后，可以添加多个条件，最常见的条件是：>,<,>=,<=,!=(或<>) between...and,like,is null,and,or,not,in
#
```

#### 			2）实例：

1.  查询出工资大于1500的所有员工的信息。

    ```mysql
    select * from emp where sal>1500;
    ```

2.  查询出工资大于（等于）1500并且小于（等于）3000的所有员工的信息

    ```mysql
    select * from emp where sal>1500 and sal<3000;
    select * from emp where sal between 1500 and 3000;
    ```

3.  查询每个月可以获得奖金的员工

    ```mysql
    select * from emp where comm is not null and comm>0;
    ```

4.  查询没有奖金的员工

    ```mysql
    select * from emp where comm is null or comm=0;
    ```

5.  查询出，基本工资大于1500，同时可以领取奖金的人

    ```mysql
    select *from emp where sal>1500 and comm>0;
    ```

6.  查询出，基本工资不大于1500，同时不可以领取奖金的人

    ```mysql
    select * from emp where sal<=1500 and (comm=0 or comm is null);
    select * from emp where not(sal>1500 and comm>0);
    ```

7.  查询出在1981年雇佣的员工信息

    ```mysql
    select * from emp where hiredate between '1981-1-1' and '1981-12-31';
    ```

8.  查询员工姓名为SMITH的员工

    ```mysql
    select * from emp where name='SMITH';
    ```

9.  查询出员工编号是7369，7698，7876的员工

    ```mysql
    select * from emp where empno=7369 or empno=7698 or empno=7976;
    select * from emp where empno in(7369,7698,7876);
    ```
    
10.  模糊查询

     ```mysql
     #通配符:%(匹配任意长度)    _(匹配一个长度)
     #查询出员姓名第二个字母包含L的员工信息
     select *from emp where ename like '_L%';
     
     #查询出员姓名包含M的员工信息
     select *from emp where ename like '%M%';
     
     #查询出在1981年雇佣的员工信息
     select * from emp where hiredate like '%81%';
     ```

11.  员工编号不等于7369的员工

     ```mysql
     select * from emp where empno !=7369;
     select * from emp where empno <>7369;
     ```


### 		3、查询排序(order by)

#### 			1）语法

```mysql
select 【 distinct】*|字段1 别名,字段2 别名,…… from 表名 别名
【 where 条件】 order by 字段1 asc,字段2 desc,……;
#	asc :升序 从低到高 (默认)
# 	desc :降序 从高到低
#	多字段排序，后续字段只在前一字段的值相同时发挥作用
```

#### 			2）实例：

```mysql
select * from emp order by sal desc;

#查询出20部门的员工，查询的信息按照工资由高到低排序，如果工资相等，则按照雇佣日期由早到晚排序
select * from emp where deptno=20 order by sal desc,hiredate asc;
```

### 		4、多表查询

#### 			1）语法

```mysql
select 【 distinct】*|字段1 别名,字段2 别名,…… from 表名1 别名,表名2 别名 【 where 条件】 order by 字段1 asc,字段2 desc,……;

#	在多表查询中，不同的表有相同的名称时，访问这个字段，必须加上表名。
SELECT * FROM emp,dept WHERE emp.deptno = dept.deptno;

#	可以使用起别名形式
SELECT * FROM emp  e,dept d WHERE e.deptno = d.deptno;

#	或者
SELECT * FROM emp as e,dept as d WHERE e.deptno = d.deptno;
```

#### 			2）实例：

1.  查询每一位员工的编号，姓名，职位，部门名称，部门位置

    ```mysql
    #分析：需要两张emp表，dept表
    #确定需要查询的表：
    	emp e1,emp e2,dept d
    	
    #确定需要查询的数据：
    	e1.empno,e1.ename,e1.sal,e1.job,e2.ename,d.dname,d.loc
    	
    #确定关联的字段
    	e1.mgr = e2.empno AND e1.deptno = d.deptno
    
    select e.empno,e.ename,e.job,d.dname,d.loc from emp e,dept d where e.deptno=d.deptno;
    ```

2.  查询每一位员工的姓名，职位，领导的姓名

    ```mysql
    #分析：需要两张emp表
    #确定需要查询的表：
    	emp e1,emp e2
    	
    #确定需要查询的数据：
    	e1.ename,e1.job,e2.ename
    	
    #确定关联的字段
    	e1.mgr = e2.empno
    	
    select e1.ename,e1.job,e2.ename from emp e1,emp e2 where e1.mgr=e2.empno;
    ```

3.  查询每个员工的编号，姓名，基本工资，职位，领导的姓名，部门名称，位置

    ```mysql
    #分析：需要两张emp表，dept表
    #(1)确定需要查询的表：
    	emp e1,emp e2,dept d
    	
    #(2)确定需要查询的数据：
    	e1.empno,e1.ename,e1.sal,e1.job,e2.ename,d.dname,d.loc
    	
    #(3)确定关联的字段
     	e1.mgr = e2.empno AND e1.deptno = d.deptno
     	
     select e1.empno,e1.ename,e1.sal,e1.job,e2.ename,d.dname,d.loc from emp e1,emp e2,dept d where e1.mgr = e2.empno and e1.deptno = d.deptno;
    ```

4.  查询每个员工的编号，姓名，工资，部门名称，工资所在公司的工资等级

    ```mysql
    #分析：需要两张emp表，dept表，salgrade表
    #(1)确定需要查询的表：
    	emp e,dept d,salgrade s
    	
    #(2)确定需要查询的数据：
    	e.empno,e.ename,e.sal,d.dname,s.grade
    	
    #(3)确定关联的字段
    	e.deptno = d.deptno AND e.sal BETWEEN s.losal AND s.hisal
    	
    select e.empno,e.ename,e.sal,d.dname,s.grade from emp e,dept d,salgrade s where e.deptno = d.deptno and e.sal between s.losal and s.hisal;
    
    ```

#### 3）左右连接

```mysql
#语法：
	主表 left 【 outer】 join 次表 on #左（外）连接
	次表 right 【 outer】 join 主表 on #右（）连接
	
#实例：
select * from emp left outer join dept on(emp.deptno=dept.deptno);
select * from emp right outer join dept on(emp.deptno=dept.deptno);

#其他连接(了解)
cross join 交叉连接 ：产生笛卡尔积
select * from emp cross join dept;
natural join 自然连接：自动关联相关联的字段，消除笛卡尔积
select * from emp natural join dept;
join...using 用户指定一个字段消除笛卡尔积
select * from emp join dept using(deptno);
join...on 指定一个条件消除笛卡尔积
select * from emp join dept ON(emp.deptno=dept.deptno);
```



### 		5、统计函数

#### 			1）语法

```mysql
count(字段) #统计表中的记录数
avg(字段) #求平均值
sum(字段) #求和
max(字段) #求最大值
min(字段) #求最小值
```

#### 			2）实例：

```mysql
#统计出公司所有员工的每个月平均工资和总工资
select count(empno),sum(sal),avg(sal) from emp;

#统计员工的最高工资和最低工资
select max(sal),min(sal) from emp;
```

### 		6、分组查询(group by)

#### 			1）语法

```mysql
select 【 distinct】 *|字段1 别名，字段2 别名...FROM 表名1 别名,表名2 别名
[where 条件]
group by 字段1，字段2...
having 条件（分组之后过滤条件）
order by 字段1 asc,字段2 desc...;
```

#### 			2）实例：

显示非销售人员的工作名称，以及从事同一工作的工资的总和，并满足从事同一工作的员工的工资总和大于等于5000，结果按照工资总和的降序排列

```mysql
#显示所有的非销售人员。
select * from emp where job<> 'SALESMAN';

#按照职位分组，并统计出每个职位的工资总和。
select job,sum(sal) from emp where job<>'SALESMAN' group by job;

#过滤工资总和小于5000的职位
select job,sum(sal) from emp where job<>'SALESMAN' group by job having sum(sal)>=5000;

#按照要求进行降序排列
select job,sum(sal) s from emp where job<>'SALESMAN' group by job having sum(sal)>=5000 order by s desc;
```

### 		7、子查询

#### 			1）实例：

1.  单行单列：

    查询比SMITH工资高的人

    ```mysql
    #1.查询SMITH的工资
    select sal from emp where ename='SMITH';
    
    #2.查出比SIMTH工资高的人
    select * from emp where sal>(select sal from emp where ename='SMITH');
    ```

    查询工资高于平均工资的员工信息

    ```mysql
    #1.查询平均工资
    select avg(sal) from emp; 
    
    #2.查询高于平均工资的员工
    select * from emp where sal>(select avg(sal) from emp);
    ```

2.  单行多列（一般少用）：

    ```mysql
    select * from emp where (job,ename)=(select job,ename from emp where ename='SMITH');
    ```

3.  多行单列:

    ```mysql
    select sal from emp where job = 'MANAGER';
    select * from emp where sal in (select sal from emp where job = 'MANAGER');
    select * from emp where sal not in (select sal from emp where job = 'MANAGER');
    
    
    
    #ANY 三种匹配形式
    #=ANY  功能和IN一样
    select * from emp where sal = any(select sal from emp where job = 'MANAGER');
    
    #>ANY 比最小值大的数据
    select * from emp where sal= any(select sal from emp where job = 'MANAGER');
    
    #<ANY 比最大值小的数据
    select * from emp where sal < any(select sal from emp where job = 'MANAGER');
    
    #ALL 两种形式
    #> ALL 比最大值大
    select * from emp where sal > all(select sal from emp where job = 'MANAGER');
    
    #< ALL 比最小值小
    select * from emp where sal < all(select sal from emp where job = 'MANAGER');
    ```

4.  from 多行多列

    查询每个部门的编号，名称，位置，部门的人数，平均工资(第三步为最终结果)

    ```mysql
    	#1.查处部门表中的信息
    select d.deptno,d.dname,d.loc from dept d;
    
    	#2.查询部门人数和平均工资 emp
    select deptno,count(empno),avg(sal) from emp e group by deptno;
    
    	#3.完成相关联操作
    select d.deptno,d.dname,d.loc,temp.c,temp.a  from dept d,(select deptno,count(empno) c,avg(sal) a from emp e group by deptno) temp where d.deptno = temp.deptno;
    
    	#4.显示结果没有40部门，使用左右连接解决。
    select d.deptno,d.dname,d.loc,temp.c,temp.a  from dept d left outer join (select deptno,count(empno) c,avg(sal) a from emp e group by deptno) temp on ( d.deptno=temp.deptno);
    ```

## 	七、MySQL函数

### 	1、字符函数

#### 		1）常用：

```mysql
#1）将字符串转化为大写返回
	upper(字符串|字段) 
	
#2）将字符串转化为小写返回
	lower(字符串|字段) 
	
#3）求字符串的长度
	length(字符串|字段) 
	
#4）替换字符串
	replace(字符串|字段,旧字符串,新字符串) 
	
#5）截取字符串
	substr(字符串|字段,开始点【，截取长度(不写默认全部)】)
	
#6）连接多个字符串成为一个字符串
	#返回来自于参数连结的字符串。如果任何参数是NULL，返回NULL。可以有超过2个的参数。一个数字参数被变换为等价的字符串形式。
		concat(字符串|字段1,字符串|字段2,...) 
		
		
#7）#从指定位置开始，返回子串在字符串或字段中第一个出现的位置，如果子串不在其中，返回0.	
	locate(子串，字符串|字段,【位置(不写默认从头)】) 

#8）字符串填充
	#返回字符串或字段，在左侧用填补字符串填补直到该字符串的长度为总长。
		lpad(字符串|字段,总长,填补字符串) 
    #返回字符串或字段，在右侧用填补字符串填补直到该字符串的长度为总长。   
		rpad(字符串|字段,总长,填补字符串) 
		
#9）返回字符串str的最左面len个字符
	left(str,len) 
	
#10）返回字符串str的最右面len个字符
	right(str,len) 
	
#11)删除空格或指定字符
	#返回删除了其前置空格字符的字符串str 
		ltrim(str) 
	#返回删除了其拖后空格字符的字符串str	
		rtrim(str) 
	#返回字符串str，其所有remstr前缀或后缀被删除了。如果没有修饰符both,leading或 trailing给出，。如果remstr没被指定，空格被删除。	
		trim(【【 both(默认两边)| leading(左)| trailing(右)】        【remstr(不写则删除空格)】 from】 str)
		
#12)颠倒字符串str的顺序
	reverse(str)
```

#### 		2）不常用或功能重复(了解)：

```mysql
#1）返回字符串str的最左侧字符的ASCII代码值
	#如果str是空字符串，返回0。如果str是NULL，返回NULL
		ascii(str)
		
#2）返回子串substr在字符串str中的第一个出现的位置
									#(类似【七：1)：#7)：locate】)
	#这与有2个参数形式的LOCATE()相同,除了参数被颠倒
		instr(str,substr)
		
#3）截取子串
									#(类似【七：1)：#5)：locate】)
	#从字符串str返回一个len个字符的子串，从位置pos开始。
		substring(str,pos,len) （5类似）
	#从字符串str的起始位置返回一个子串	
		substring(str,起始位置) 
		substring(str from 起始位置) 
	#返回从字符串str的第c个出现的分隔符之后的子串。如果c是正数，返回最后的分隔符到左边(从左边数) 的所有字符。如果c是负数，返回最后的分隔符到右边的所有字符(从右边数)
		substring_index(str,分隔符,c) 
		
#4）返回由N个空格字符组成的一个字符串
	space(N)
	
#5）返回字符串str，其字符串fromstr的所有出现由字符串tostr代替
	replace(str,fromstr,tostr)
	
#6）重复c次字段输出
	#如果c <= 0，返回一个空字符串。如果str或c是null，返回null
		repeat(str,c)
		
#7）返回字符串str，将从pos位置开始，len个字符长的子串代替为字符串newstr
	insert(str,pos,len,newstr)
	
#8）如果N=1，返回str1，如果N=2，返回str2...如果N小于1或大于参数个数，返回null
											#elt()是fielt()反运算
	elt（N,str1,str2,...）
	
#9）返回str在str1, str2, str3, ...清单的索引。如果str没找到，返回0
											#fielt()是elt()反运算
	fielt（str,str1,str2,...）
```

#### 	3）实例：

```mysql
#1）将字符串转化为大写返回
	select upper('asd');
	select upper(ename) from emp;
	
#2）将字符串转化为小写返回
	select lower('asD');
	select lower(ename) from emp;
	
#3）求字符串或字段的长度
	select length('asD');
	select length(ename) from emp;
	
#4）替换字符串[replace(字符串|字段,旧字符串,新字符串)]
	#将字符串ename中的所有a替换为-
	select replace('ename','a','-');
	#将表emp中的字段ename中的所有字符串中的A替换为_
	select replace(ename,'A','_') from emp;
	
#5）截取字符串[substr(字符串|字段,开始点【，截取长度】)]
		select substr('ename',1,3);
		select substr(ename,1,3) from emp;
	截取员工名称的后三位
		select substr(ename,length(ename)-2) from emp;
		select substr(ename,-3) from emp;
	
#6）连接多个字符串成为一个字符串
	select concat(ename,empno) from emp;
	select concat('ename','empno');
	
#7）#从指定位置开始，返回子串在字符串或字段中第一个出现的位置，如果子串不在其中，返回0.[locate(子串，字符串|字段,【位置(不写默认从头)】)]
	select locate('ab','bab123ab',2);
	
#8）字符串填充[lpad|rpad(字符串|字段,总长,填补字符串)]
	select lpad('12',5,'abcdef');
	select rpad('12',5,'abcdef');
	
#9）返回字符串str的最左面len个字符[left(str,len)]
	select left('123456789',5);
		
#10）返回字符串str的最右面len个字符[right(str,len)]
	select right('123456789',5);
	
#11)删除空格或指定字符
	#ltrim|rtrim(str)trim(【【 both(默认两边)| leading(左)| trailing(右)】 【remstr(不写则删除空格)】 from】 str)
	select ltrim('   123456   ');
	select trim( both 'a' from 'a123456a');
	
#12)返回颠倒字符顺序的字符串str
	select reverse(ename) from emp;
```



### 	2、数字函数

#### 	语法

```mysql
#四舍五入
	round(数字|列，【保留小数】)

#取模，求余数
	mod(数1,数2)

#求绝对值
	abs(数字|列)

#返回参数的符号，为-1、0或1，取决于X是否是负数、零或正数
	sign(x)

#向下取整 返回不大于X的最大整数值
	floor(X)

#向上取整 返回不小于X的最小整数值
	ceiling(X)

#截断小数
	truncate(X,D) 
		#返回数字X，截断为D位小数。如果D为0，结果将没有小数点或小数部分
```

#### 	实例

```mysql
#四舍五入			round(数字|列，【保留小数】)

#取模，求余数		mod(数1,数2)

#求绝对值		abs(数字|列)

#返回参数的符号，为-1、0或1，取决于X是否是负数、零或正数		sign(x)

#向下取整	floor(X)

#向上取整	ceiling(X)

#截断小数	truncate(X,D)

```



### 	3、日期和时间

#### 	语法

```mysql
#以'YYYY-MM-DD HH:MM:SS'或YYYYMMDDHHMMSS格式返回当前的日期和时间
	now() 
		#取决于函数是在一个字符串还是在数字的上下文被使用
		#sysdate()获取系统时间

#以'YYYY-MM-DD'或YYYYMMDD格式返回今天日期值
 	curdate()
 	#取决于函数是在一个字符串还是数字上下文被使用

#以'HH:MM:SS'或HHMMSS格式返回当前时间值
	curtime() 
		#取决于函数是在一个字符串还是在数字的上下文被使用

#返回日期date的星期索引
	dayofweek(date) 
		#1=星期天，2=星期一, ……7=星期六
		
#返回date的星期索引
	weekday(date) 
		#0=星期一，1=星期二, ……6= 星期天

#返回date的月份中日期，在1到31范围内
	dayofmonth(date)

#返回date在一年中的日数, 在1到366范围内
	dayofyear(date)
	
#返回date的月份，范围1到12
	month(date)

#返回date的星期名字
	dayname(date)

#返回date的月份名字 
	monthname(date)

#返回date一年中的季度，范围1到4
	quarter(date)
	
#返回date的周数，范围在0到52（星期天是一周的第一天）
	week(date)
	#如果first=0，从星期天开始，如果first=1，从星期一开始 
		week(date,first) 

#返回date的年份，范围在1000到9999
	year(date) 

#返回time的小时，范围是0到23
	hour(time) 

#返回time的分钟，范围是0到59
	minute(time) 

#回来time的秒数，范围是0到59
	second(time) 

#增加N个月到阶段P（以格式YYMM或YYYYMM)。以格式YYYYMM返回值
	period_add(P,N) 
		#注意阶段参数P不是日期值

#返回在时期P1和P2之间月数，P1和P2应该以格式YYMM或YYYYMM
	period_diff(P1,P2)
		#注意，时期参数P1和P2不是日期值

#给出一个日期date，返回一个天数
	to_days(date) 
		#从0年的天数

#给出一个天数N，返回一个DATE值
	from_days(N)

#根据format字符串格式化date值
	date_format(date,format)

#返回unix_timestamp参数所表示的值
	from_unixtime(unix_timestamp)
		#以'YYYY-MM-DD HH:MM:SS'或YYYYMMDDHHMMSS格式返回
		#取决于函数是在一个字符串还是或数字上下文中被使用

#返回表示Unix时间标记的一个字符串，根据format字符串格式化
	from_unixtime(unix_timestamp,format) 
		#format可以包含与DATE_FORMAT()函数列出的条目同样的修饰符

#返回seconds参数，变换成小时、分钟和秒
	sec_to_time(seconds)
		#值以'HH:MM:SS'或HHMMSS格式化
		#取决于函数是在一个字符串还是在数字上下文中被使用

#返回time参数，转换成秒
	time_to_sec(time)

```

表：下列修饰符可以被用在format字符串中用以格式化

| 符号 | 作用                                           |
| ---- | ---------------------------------------------- |
| %M   | 月名字(January……December                       |
| %W   | 星期名字(Sunday……Saturday)                     |
| %D   | 有英语前缀的月份的日期(1st, 2nd, 3rd, 等等。） |
| %Y   | 年, 数字, 4 位                                 |
| %y   | 年, 数字, 2 位                                 |
| %a   | 缩写的星期名字(Sun……Sat)                       |
| %d   | 月份中的天数, 数字(00……31)                     |
| %e   | 月份中的天数, 数字(0……31)                      |
| %m   | 月, 数字(01……12)                               |
| %c   | 月, 数字(1……12)                                |
| %b   | 缩写的月份名字(Jan……Dec)                       |
| %j   | 一年中的天数(001……366)                         |
| %H   | 小时(00……23)                                   |
| %k   | 小时(0……23)                                    |
| %h   | 小时(01……12)                                   |
| %I   | 小时(01……12)                                   |
| %l   | 小时(1……12)                                    |
| %i   | 分钟, 数字(00……59)                             |
| %r   | 时间,12 小时(hh:mm:ss [AP]M)                   |
| %T   | 时间,24 小时(hh:mm:ss)                         |
| %S   | 秒(00……59)                                     |
| %s   | 秒(00……59)                                     |
| %p   | AM或PM                                         |
| %w   | 一个星期中的天数(0=Sunday ……6=Saturday ）      |
| %U   | 星期(0……52), 这里星期天是星期的第一天          |
| %u   | 星期(0……52), 这里星期一是星期的第一天          |
| %%   | 一个文字“%”。                                  |

### 	4、其他函数

#### 	语法

```mysql
#返回当前的数据库名字
	database()

#返回当前MySQL用户名
	user()
	system_user()
	session_user()

#对字符串计算md5校验和。值作为一个32长的十六进制数字被返回可以
	md5(string)

#格式化数字X为类似于格式'#,###,###.##'，四舍五入到D为小数
	format(X,D)
		#如果D为0，结果将没有小数点和小数部分
#返回表明MySQL服务器版本的一个字符串
	version()

#将指定字段的null值替换为指定值
	ifnull(字段,值)
```

### 	5、

## 	八、MySQL事务

MySQL默认事务会自动开启并自动提交

```mysql
#关闭自动提交：
set autocommit = 0;

#开启自动提交：
set autocommit = 1;

#手动提交：
commit;

#开启事务：
start transaction;

#事务回滚：
rollback
```

### 四大特征：原子性

事务开始后所有操作，要么全部做完，要么全部不做，不可能停滞在中间环节。事务执行过程中出错，会回滚到事务开始前的状态，所有的操作就像没有发生一样。

### 四大特征：一致性

—致性是指事务必须使数据库从一个—致性状态变换到另一个—致性状态，也就是说一个事务执行之前和执行之后都必须处于一致性状态。举例来说，假设用户A和用户B两者的钱加起来一共是1000，那么不管A和B之间如何转账、转几次账，事务结束后两个用户的钱相加起来应该还得是1000，这就是事务的一致性。

### 四大特征：隔离性

同一时间，只允许一个事务请求同一数据，不同的事务之间彼此没有任何干扰。比如A正在从一张银行卡中取钱，在A取钱的过程结束前，B不能向这张卡转账。

#### 事务的隔离级别:

1.  Read uncommitted(未授权读取、读未提交)：最低级别，任何情况都无法保证
2.  Read committed（授权读取、读已提交）可避免**脏读**的发生 （Orcale默认的隔离级别）
3.  Repeatable read（可重复读取）：可避免**脏读**、**不可重复读**的发生 （mysql**默认**的隔离级别）
4.  Serializable（可串行化）：可避免**脏读**、**不可重复读**、**幻读**的发生

```mysql
#查询隔离级别：
Select @@tx_isolation;

#修改默认隔离级别：
Set [global | session] transaction isolation level 隔离级别名称;
	#global:全局修改但必须重开数据库	session:只在当前库有效，不必重开

#修改隔离级别：
Set global transaction isolation level Read uncommitted;
Set global transaction isolation level Read committed;
Set global transaction isolation level Repeatable read;
Set global transaction isolation level Serializable;

```



### 四大特征：持久性

指一个事务一旦提交，它对数据库中数据的改变就应该是永久性的。接下来的其他操作或故障不应该对其执行结果有任何影响。

## 	九、JDBC

1.  JDBC连接数据库的基本步骤：
2.  下载MySQL驱动
3.  将MySQL启动导入项目，并执行“Add As Library…”命令
4.  加载驱动
5.  由驱动管理器获取连接
6.  由连接获取数据库操作对象：PreparedStatement
7.  执行sql语句（如果sql语句中有?占位符，需要在执行前替换）
8.  关闭连接

```java
package com.Mar.test;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class Test {
    public static void main(String[] args) throws ClassNotFoundException, SQLException {
        //加载驱动器
        Class.forName("com.mysql.jdbc.Driver");
        
        //url: "jdbc:mysql://数据库ip地址:端口号/数据库名称"
        String url = "jdbc:mysql://localhost:3306/sjt2207";//数据库地址
        String usename = "root";//用户名
        String password = "root";//密码
        
        //驱动管理器获取连接
        Connection connection = DriverManager.getConnection(url, usename, password);

        //连接获取数据库操作对象
        String sql = "insert into test values (null,?,?,?)";//?占位
        PreparedStatement ps = connection.prepareStatement(sql);
        
        //替换sql中的?占位符
        //ps.set类型(位置,数据)
        ps.setString(1,"张三");
        ps.setString(2,"123456");
        ps.setInt(3,25);
        
        //执行sql语句
        ps.execute();//可执行所有操作
        ps.executeUpdate();//执行更新操作，包括：修改，添加和删除
        ps.executeQuery();//执行查询操作
        
        //关闭连接
        connection.close();
    }
}
```

## 	十、
