#### java jdk安装

##### 1.准备文件   

> Mac平台准备 jdk-8u151-macosx-x64.dmg
> 
> Linux平台 jdk-8u151-linux-x64.tar.gz


##### 2.安装   


```
	# Linux 平台安装 
	sudo cp ./jdk-8u151-linux-x64.tar.gz  /usr/local
	cd /usr/local
	sudo tar -zxvf jdk-8u151-linux-x64.tar.gz
	
	# MAC 平台安装 
	直接进行jdk-8u151-macosx-x64.dmg 安装

```
这个时候已经可以看到在"/usr/local" 有java的一个目录了

检验java版本

```    
	# Linux 平台
	cd /usr/local/java/bin
	./java -version  
	
	# MAC 平台
	java -version

```    

 提示内容如下 说明golang安装包正常      
           
```          
 	 
java version "1.8.0_111"
Java(TM) SE Runtime Environment (build 1.8.0_111-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.111-b14, mixed mode)  

```


配置环境变量

```    
sudo vim /etc/profile
```  
在文件末尾增加上下边三行，保存并退出. 

###### Linux 平台

```
export JAVA_HOME=/usr/local/java
export PATH=$JAVA_HOME/bin:$PATH

```

###### MAC 平台

```
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_111.jdk/Contents/Home/

```

环境变量立即生效

```
> source /etc/profile

```
