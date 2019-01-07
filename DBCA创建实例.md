# oracle DBCA 启动数据库
[参考文档](https://blog.csdn.net/lvshaorong/article/details/78048823)
## 1. 到Oracle的bin目录下，使用oracle用户，执行dbca即可

## 2. 在弹出的图形界面中创建实例
### 选择创建数据库实例
![1](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA1.png?raw=true)

### 选择高级配置（经典配置在实际使用时容易出现问题）
![2](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA2.png?raw=true)

### 选择单实例数据库，用于一般用途或事物处理
![3](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA3.png?raw=true)

### 设置全局数据库名和SID，不勾选容器数据库选项
![4](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA4.png?raw=true)

### 默认
![5](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA5.png?raw=true)

### 快速恢复区
![6](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA6.png?raw=true)

### 一般使用oracle默认自建的LISTENER即可，使用默认1521端口
如果你想使用别的端口，或者多个端口，就勾选下面的创建新监听程序。一般推荐创建一个新的，以后改起端口来方便。  
![7](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA7.png?raw=true)

### Data Vault选项保持默认（全都不勾选）即可

### 关键，设置内存、进程、字符集
![8](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA9.png?raw=true)


### 设置口令
![9](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA10.png?raw=true)


### 可以保存创建模板
![10](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA11.png?raw=true)

### 浏览用，概要
![11](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA12.png?raw=true)

![12](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA13.png?raw=true)

![13](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA14.png?raw=true)

![14](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA15.png?raw=true)

![15](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA16.png?raw=true)

## 连接实例
![16](https://github.com/cnxz43/tech-doc/blob/master/pic/DBCA17.png?raw=true)