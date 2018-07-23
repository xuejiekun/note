# MySQL Note
***

## chapter 1
### 选择数据库
* use database;
### 显示数据库
* show database;
### 显示表
* show tables;
### 显示表列
* show columns from `table_name`;
* describe `table_name`;
***

## chapter 2
### 检索单个列
* select `col_1`  
  from `table_name`;
### 检索多个列
* select `col_1`, `col_2`, `col_3`  
  from `table_name`;
### 检索所有列
* select *   
  from `table_name`;
### 不同的行
* select distinct `col_1`  
  from `table_name`;

### 限制结果
#### 显示num行  
* select `col_1`  
  from `table_name`  
  limit `num`;  
#### 从col_num开始的num行  
* select `col_1`  
  from `table_name`  
  limit `col_num`, `num`;
***

## chapter 3
### 排序数据
* select `col_1`  
  from `table_name`  
  order by `col_1`;
### 按多个列排序
* select `col_1`, `col_2`  
  from `table_name`  
  order by `col_1`, `col_2`;
### 降序排序
* select `col_1`  
  from `table_name`  
  order by `col_1` desc;
***

## chapter 4
### where子句
* select `col_1`  
  from `table_name`  
  where `col_1 = xxx`;

### where操作符
| 操作符  | 说明       |
| :-----: | :--------: |
| =       | 等于       |
| <>      | 不等于     |
| !=      | 不等于     |
| <       | 小于       |
| <=      | 小于等于   |
| >       | 大于       |
| >=      | 大于等于   |
| between | 两个值之间 |

### between
* select `col_1`  
  from `table_name`  
  where `col_1` between `xxx` and `yyy`;
### 空值检查
* select `col_1`  
  from `table_name`  
  where `col_1` is null;
***

## chapter 5
### and操作符
* select `col_1`  
  from `table_name`  
  where `col_1 = xxx` and `col_2 = yyy`;
### or操作符
* select `col_1`  
  from `table_name`  
  where `col_1 = xxx` or `col_2 = yyy`;
### 注意优先级，使用圆括号
### in操作符
* select `col_1`  
  from `table_name`  
  where `col_1` in `(xxx, yyy)`;
***

## chapter 6
### 通配符
* select `col_1`  
  from `table_name`  
  where `col_1` like `'str'`;

| 通配符 | 匹配字符数      |
| :----: | :-------------: |
| %      | 任意个数,[0,+∞) |
| _      | 单个字符        |

### 正则表达式
* select `col_1`  
  from `table_name`  
  where `col_1` regexp `'pattern'`;
***

## chapter 7
### 文本处理函数
| 名称                  | 作用                     |
| :-------------------- | :----------------------- |
| concat(str1,str2,...) | 连接字段                 |
| length(str)           | 串的长度                 |
| locate(sub,str)       | 返回子串第一次出现的位置 |
| substring()           | 返回子串字符             |
| ltrim(str)            | 去掉串左边空格           |
| rtrim(str)            | 去掉串右边空格           |
| left()                | 返回串左边字符           |
| right()               | 返回串右边字符           |
| lower(str)            | 将串转为小写             |
| upper(str)            | 将串转为大写             |
| soundex(str)          | 返回soundex数值          |

### 聚集函数
| 名称    | 作用   |
| :------ | :----- |
| avg()   | 平均值 |
| count() | 行数   |
| max()   | 最大值 |
| min()   | 最小值 |
| sum()   | 总和   |

### 聚集不同的值(使用distinct)
* select avg(distinct `col_1`)  
  from `table_name`;
***

## chapter 8
### 数据分组
* select `col_1`, count(*)  
  from `table_name`  
  group by `col_1`;  
  (以col_1分组，计算每组的行数)
### 过滤分组
* select `col_1`, count(*)  
  from `table_name`  
  group by `col_1`  
  having count(\*) = `xxx`;
### select子句顺序
| 子句     | 说明       |
| :------- | :--------- |
| select   | 列或表达式 |
| from     | 检索的表   |
| where    | 行级过滤   |
| group by | 指定分组   |
| having   | 组级过滤   |
| order by | 排序       |
| limit    | 检索行数   |
***

## chapter X
### 插入完整的行
#### 依赖参数顺序
* insert into `table_name`  
  values `(param1, param2, param3)`;  
#### 不依赖参数顺序
* insert into `table_name`  
  `(col_1, col_2, col_3)`  
  values `(param1, param2, param3)`;
#### 降低优先级
* insert **low_priority** into

### 插入多个行
* insert into `table_name`  
  `(col_1, col_2, col_3)`  
  values `(param1, param2, param3)`,  
  `(param1, param2, param3)`,  
  `(param1, param2, param3)`;

### 插入检索数据
* insert into `table_name`  
  `(col_1, col_2, col_3)`  
  select `col_1, col_2, col_3`  
  from `table_name`;
***

## chapter XX
### 更新数据
* update `table_name`  
  set `col_1 = xxx`  
  where `col_2 = yyy`;
### 删除数据
* delete `table_name`   
  where `col_1 = xxx`;
### 删除所有数据
* truncate table `table_name`;
***

## chapter XXX
### 创建表
```sql
create table table_name
(
    col_1   date_type   null  auto_increment,
    col_2   date_type   null                ,
    col_3   date_type   not null            ,
    primary key(col_1)
)engine=InnoDB;
```
### 更新表
#### 添加一个列
* alter table `table_name`  
  add `col_1` date_type;
#### 删除一个列
* alter table `table_name`  
  drop column `col_1`;
### 删除表
* drop table `table_name`;
### 重命名表
* rename table `table_name` to `table_name_new`;
***

## chapter XXXX
### 执行存储过程
* call `_proc(@var1, @var2, @var3)`;

### 创建存储过程
```sql
delimiter //
create procedure _proc()
begin
  -- 子句
end //
delimiter ;
```
### 删除存储过程
* drop procedure `_proc` if exists;

### 使用参数
```sql
delimiter //
create procedure _proc(
  in param1 data_type,
  out var1 data_type,
)
begin
  -- 子句
  select avg(col_1)
  from table_name
  into var1;
end //
delimiter ;
```
***

## chapter XXXXX
### 用户表
* select user from user;
### 创建用户
* create user `user_name` identified by `'password'`;
### 重命名用户
* rename user `user_name` to `user_name_new`;
### 删除用户
* drop user `user_name`;

### 显示权限
* show grants for `user_name`;
### 设置权限
* grant `privileges` on `area_name` to `user_name`;

| 层次设置       |
| :------------: |
| 整个服务器     |
| 整个数据库     |
| 特定的表       |
| 特定的列       |
| 特定的存储过程 |

### 撤销权限
* revoke `privileges` on `area_name` from `user_name`;

### 更改密码
* set password for `user_name` = password(`'password'`);