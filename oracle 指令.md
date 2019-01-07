1. 先看oracle的监听和oracle的服务是否都启动了。启动oracle监听：
cmd的命令行窗口下，输入lsnrctl start，回车即启动监听。

```
lsnrctl start

```

2. 查看oracle的sid叫什么，比如创建数据库的时候，实例名叫“abc”，那么先手工设置一下oralce的sid，cmd命令窗口中，set ORACLE_SID=abc
```
```
3. 再输入sqlplus  /nolog,回车
再输入 conn / as sysdba;回车
```
sqlplus  /nolog
conn / as sysdba;
```
4. 再输入startup，回车.这步是启动oracle服务。如果startup启动被告知已经启动了，可以先输入shutdown immediate；等shutdown结束之后，再输入startup。