---
title: linux安装PostgreSQL
date: 2022-10-31 15:53:19
tags: PostgreSQL
cover: https://bing.ioliu.cn/v1/rand?w=400&h=300
---





## 参考

[(106条消息) linux安装PostgreSQL步骤，亲测有效_Dark Sky.的博客-CSDN博客_linux安装postgresql](https://blog.csdn.net/Dark_Blue__/article/details/125187959)


## 安装准备

用户准备
新建一个非root用户，比如这里是 vagrant，且打算将pg库安装在vagrant家目录下

安装目录准备

``` 
mkdir -p /home/vagrant/postgresql
mkdir -p /home/vagrant/postgresql/data
mkdir -p /home/vagrant/postgresql/log

```
## 1、下载

https://ftp.postgresql.org/pub/source/v14.2/postgresql-14.2.tar.gz



解压缩

```
tar -zxvf postgresql-14.2.tar.gz -C /home/vagrant/postgresql-14.2
```






## 2、yum所需

```
yum -y install gcc-c++
yum -y install -y readline-devel
```

在`/home/vagrant/postgresql-14.2/`目录下执行

```
./configure --prefix=/home/vagrant/postgresql
```



```
make && make install
```



```
vi /etc/profile
```



添加
``` 
export PGHOME=/home/vagrant/postgresql
export PGDATA=/home/vagrant/postgresql/data
export PATH=$PATH:$PGHOME/bin:$PGDATA/bin
```



```
source /etc/profile


```



```
/home/vagrant/postgresql/bin/initdb -D /home/vagrant/postgresql/data/
```







```
vi /home/vagrant/postgresql/data/postgresql.conf
```



把60行的listen_addresses = 'localhost’ 改为listen_addresses = '*'
把对应的port=5432注释放开，并可自行修改端口号

```
vi /home/vagrant/postgresql/data/pg_hba.conf
```



在最后一行添加



```
host all all 0.0.0.0/0 trust
```







```
说明：
TYPE：pg的连接方式，local：本地unix套接字，host：tcp/ip连接
DATABASE：指定数据库
USER：指定数据库用户
ADDRESS：ip地址，可以定义某台主机或某个网段，32代表检查整个ip地址，相当于固定的ip，24代表只检查前三位，最后一 位是0~255之间的任何一个
METHOD：认证方式，常用的有ident，md5，password，trust，reject。
md5是常用的密码认证方式。
password是以明文密码传送给数据库，建议不要在生产环境中使用。
trust是只要知道数据库用户名就能登录，建议不要在生产环境中使用。
reject是拒绝认证。


```







```
/home/vagrant/postgresql/bin/pg_ctl start -l /home/vagrant/postgresql/log/pg_server.log
```

![启动命令](/imgs/2022-11-13/xuDxrBEd9PWDRrVU.png)




使用数据库连接工具测试连接即可

## 常用命令

停止服务
```
./bin/pg_ctl stop 
```

启动服务
```
pg_ctl start -l ./log/pg_server.log
```

```
192.168.0.109 
数据库：postgres
oyaji/postgres
```

## 添加用户

PostgreSQL创建用户与授权操作

https://blog.csdn.net/GISuuser/article/details/124834504


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg2MjkwNDMyNywxNDY1MjY2ODU2XX0=
-->