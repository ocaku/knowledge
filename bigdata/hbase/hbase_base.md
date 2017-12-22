## namespace

#### hbase系统默认定义了两个缺省的namespace  
hbase：系统内建表，包括namespace和meta表   
default：用户建表时未指定namespace的表都创建在此  

####  namespace操作命令  
创建namespace : create_namespace 'name'  
删除namespace : drop_namespace 'name'  
查看namespcae ：describe_namespace 'name'  
列出所有的namespace :“list_namespace”
