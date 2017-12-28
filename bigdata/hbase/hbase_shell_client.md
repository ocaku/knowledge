#### hbase client  

##### 1.准备文件   

> hbase-1.3.1-bin.tar.gz  
> 下载地址:http://mirrors.shuosc.org/apache/hbase/


##### 2.安装   

```
	# Linux 平台安装 
	sudo cp ./hbase-1.3.1-bin.tar.gz  /data/app
	cd /data/app
	sudo tar -zxvf hbase-1.3.1-bin.tar.gz
```    
这个时候已经可以看到在"/data/app" 有"hbase-1.3.1"的一个目录了

先检测java版本,以及JAVA_HOME环境变量,在进行下一步.

```    
	cd /data/app/hbase-1.3.1
	vim ./conf/hbase-site.xml   
```    
#### hbase-site.xml 中的配置
只限于hbase shell client ,增加hbase节点配置不按照此配置.
##### 单节点本地配置

```   
<configuration>
  <property>
    <name>hbase.rootdir</name>
    <value>file:///home/testuser/hbase</value>
  </property>
  <property>
    <name>hbase.zookeeper.property.dataDir</name>
    <value>/home/testuser/zookeeper</value>
  </property>
</configuration>
```    


##### 单节点远程配置

```   
<configuration>
  <property>
    <name>hbase.rootdir</name>
    <value>hdfs://namenode.example.org:8020/hbase</value>
  </property>
  <property>
    <name>hbase.zookeeper.property.dataDir</name>
    <value>/home/testuser/zookeeper</value>
  </property>
</configuration>
```    

##### 远程集群配置   

```   
	<configuration>
	  <property>
	    <name>hbase.cluster.distributed</name>
	    <value>true</value>
	  </property>
	  <property>
	    <name>hbase.zookeeper.quorum</name>
	    <value>node-a.example.com,node-b.example.com,node-c.example.com</value>
	  </property>
	</configuration>
```    
> node-a.example.com 是hbase的zk节点地址   
> 在hosts 增加上hbase集群的host 


##### 进入hbase客户端

```    
cd /data/app/hbase-1.3.1
./bin/hbase shell
```  
如果一切顺利的话,这个时候就可以开启你的hbase shell client 操作数据了.
