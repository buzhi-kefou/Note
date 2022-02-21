# 深入浅出MySQL
ISAM:Indexed Sequential Access Method(索引顺序存取方法)  
LAMP:Linux Apache MySQL PHP  
RPM:Redhat Package Manager  
GPL:GNU General Public License
## 基础篇
- 安装与配置
- SQL基础
- 数据类型
- 运算符
- 常用函数
- 图形工具
### MySQL的安装与配置
#### 下载
网页直接下载  
命令行方式下载
#### 安装
图形化界面安装  
命令行方式安装
#### 配置
图形化界面配置  
修改配置文件配置
#### 启动与关闭
windows命令行启动
```shell
#创建my.ini，写入默认配置
[mysqld] 
# 设置 3306 端口 
port=3306 
# 设置 mysql 的安装目录 
basedir=E:\\Mysql\\mysql-8.0.19-winx64 
# 设置 mysql 数据库的数据的存放目录
datadir=E:\\Mysql\\mysql-8.0.19-winx64\\data 
# 允许最大连接数 
max_connections=200 
# 允许连接失败的次数。这是为了防止有人从该主机试图攻击数据库系统 
max_connect_errors=10 
# 服务端使用的字符集默认为 UTF8 
character-set-server=utf8 
# 创建新表时将使用的默认存储引擎 
default-storage-engine=INNODB 
# 默认使用“mysql_native_password”插件认证 
default_authentication_plugin=mysql_native_password 
[mysql] 
# 设置 mysql 客户端默认字符集 
default-character-set=utf8 
[client] 
# 设置 mysql 客户端连接服务端时默认使用的端口 
port=3306 
default-character-set=utf8
#配置环境变量MySQL_HOME
MySQL=E:\\Mysql\\mysql-8.0.19-winx64
#创建data目录
mysqld --initialize-insecure
#初始化语句
mysqld --defaults-file=E:\Mysql\mysql-8.0.19-winx64\my.ini --initialize -–console
#安装mysql
mysqld install
#创建root用户
mysqld --initialize-insecure --user=mysql
#启动服务
net start mysql
#登录用户
mysql -u root -p
#创建用户与授权
use mysql;
truncate table user;
flush privileges;
create user 'root'@'%' identified by  'password';
grant all privileges on *.* to 'root'@'%' with grant option;
flush privileges;
#停止服务
net stop mysql
```
linux命令行启动
```shell
service mysql start
service mysql stop
```
### SQL基础
#### 简介
SQL:Structure Query Language(结构化查询语言)  
20世纪80年代初，美国国家标准局(ANSI,American National Standards Institute)开始着手制定SQL标准，最早的ANSI标准在1986年完成，称为SQL-86。
#### 使用入门
- 分类
  - DDL:Data Definition Languages.数据定义语言，定义了不同的数据库对象，常用的关键字create、alter、drop等。
  - DML:Data Manipulation Languages.数据操纵语言，用于添加、删除、更新、查询数据库记录，检查数据完整性，常用的关键字insert、delete、update、select等。
  - DCL:Data Control Languages.数据控制语言，用于控制访问权限和安全级别，常用的关键字grant、revoke等。
- DDL
  > create database name;  
  > show databases;  
  > information_schema存储系统中的数据库对象信息  
  > performance_schema存储系统的执行性能信息  
  > mysql存储系统的用户权限信息  
  > sys存储系统的调优和诊断信息  
  > use name;  
  > show tables;  
  > drop database name;  
  > create table name (  
  >   column1 type1 constraints1,  
  >   column2 type2 constraints2  
  > )