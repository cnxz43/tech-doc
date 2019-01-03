# RedHat Oracle Database 12c Release 2 安装

## 环境： mac + Parallels Desktop + Redhat 7.2
[数据库下载地址](https://www.oracle.com/technetwork/database/enterprise-edition/downloads/oracle12c-linux-12201-3608234.html)
12c Release 2 只有一个文件

![安装过程1](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-02%20下午3.42.05.png?raw=true)
![安装过程2](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-02%20下午3.42.08.png?raw=true)

## 创建用户

```
# /usr/sbin/groupadd oinstall
# /usr/sbin/groupadd dba
# /usr/sbin/useradd -g oinstall -G dba oracle
# passwd oracle
```

## 修改参数

### 内核参数 vi /etc/sysctl.conf 
```
fs.aio-max-nr = 1048576
fs.file-max = 6815744
kernel.shmall = 2097152
kernel.shmmax = 536870912
kernel.shmmni = 4096
kernel.sem = 250 32000 100 128
net.ipv4.ip_local_port_range = 9000 65500
net.core.rmem_default = 262144
net.core.rmem_max = 4194304
net.core.wmem_default = 262144
net.core.wmem_max = 1048586

```
应用配置
```
/sbin/sysctl -p
```

### 用户限制 vi /etc/security/limits.conf
```
oracle           soft    nproc   2047
oracle           hard    nproc   16384
oracle           soft    nofile  1024
oracle           hard    nofile  65536
```

### 用户验证选项 vi /etc/pam.d/login

```
session    required     pam_limits.so
```

### 用户配置文件 vi /etc/profile

```
if [ $USER = "oracle" ] ; then
	if [ $SHELL = "/bin/ksh" ] ; then
		ulimit -p 16384
		ulimit -n 65536
	else
		ulimit -u 16384 -n 65536
	fi
fi

```



## 创建安装目录
```
# mkdir -p /u01/
# chown -R oracle:oinstall /u01/
# chmod -R 775 /u01/
```

## 修改用户bash shell
```
export ORACLE_BASE=/u01/app
export ORACLE_HOME=$ORACLE_BASE/oracle
export ORACLE_SID=liusuping
export PATH=$ORACLE_HOME/bin:$PATH:$HOME/bin
```

## 解决 安装oracle的时候出现的问题DISPLAY not set! 

```
#xhost +

# su - oracle

# export DISPLAY=:0.0
```

## 安装数据库
```
# 进入数据库文件目录

#./runInstaller
```

![1](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.27.18.png?raw=true) 
![2](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.29.19.png?raw=true) 
![3](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.29.25.png?raw=true) 
![4](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.29.32.png?raw=true) 
![5](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.31.59.png?raw=true) 
![6](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.32.13.png?raw=true) 
![7](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.32.33.png?raw=true) 
![8](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.32.49.png?raw=true) 
![9](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.33.09.png?raw=true) 
![10](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.33.30.png?raw=true) 
![11](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.34.37.png?raw=true) 
![12](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.47.24.png?raw=true) 
![13](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.48.48.png?raw=true) 
![14](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.49.07.png?raw=true) 
![14](https://github.com/cnxz43/tech-doc/blob/master/pic/屏幕快照%202019-01-03%20上午10.54.57.png?raw=true) 

