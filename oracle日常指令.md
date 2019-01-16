# oracle 日常指令

[参考](https://www.cnblogs.com/ios9/p/8708954.html)

## 启动EM
```
$ORACLE_HOME/bin/emctl start dbconsole

http://localhost.localdomain:5500/em/console/

emctl start dbconsole
emctl stop dbconsole
emctl status dbconsole
```


## 启动监听
```
lsnrctl start

 lsnrctl stop
```

## 启动数据库
```
sqlplus / as sysdba

oracle@suse92:~> sqlplus /nolog
SQL*Plus: Release 9.2.0.4.0 - Production on Fri Jan 20 02:29:37 2006
Copyright (c) 1982, 2002, Oracle Corporation. All rights reserved.
SQL> connect /as sysdba
Connected to an idle instance.
SQL> startup
ORACLE instance started.
Total System Global Area 135352820 bytes
Fixed Size 455156 bytes
Variable Size 109051904 bytes
Database Buffers 25165824 bytes
Redo Buffers 679936 bytes
Database mounted.


oracle@suse92:~> sqlplus /nolog
SQL*Plus: Release 9.2.0.4.0 - Production on Fri Jan 20 02:29:37 2006
Copyright (c) 1982, 2002, Oracle Corporation. All rights reserved.
SQL> connect /as sysdba
Connected to an idle instance.
SQL> shutdwon abort;
```




## 修改参数
```
# SQL*Plus
alter system 

# 例：
alter system set db_create_file_dest='c:\oradata' scope=both

# 参数文件
pfile 和 spfile 转换
create spfile [='spfilename'] from pfile [='pfilename'];
create pfile [='pfilename'] from spfile [='spfilename'];

CREATE PFILE
CREATE SPFILE
```

