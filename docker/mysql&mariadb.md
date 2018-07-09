### docker run mysql/mariadb

首次启动

```
mkdir -p /data/mysql/data  #挂载本地data目录到 容器中的位置 mysql

docker run --name mysql -p 3306:3306 -v /data/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD='root' -d mysql
```
加载MySQL本地数据
``` 
docker run --name mysql -p 3306:3306 -v /data/mysql/data:/var/lib/mysql -d mysql
```

如需自定义配置增加参数:

```
 -v /etc/mysql/conf.d:/etc/mysql/conf.d
```
 
如果出现
ERROR 2059 (HY000): Authentication plugin 'caching_sha2_password' cannot be loaded: /usr/local/mysql

```
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY 'root'; # 修改加密算法

FLUSH PRIVILEGES;
```

直接连接MySQL 

```
docker exec -it mysql bash -c 'mysql -uroot -p '
```

常用命令

```
docker ps -a
docker rm mysql 
```
