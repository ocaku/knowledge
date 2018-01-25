### memcached telnet

#### telnet链接

telnet 127.0.0.1 11211

#### telnet请求命令格式     

```
<command name> <key> <flags> <exptime> <bytes>\r\n <data block>\r\n

```

|Command	|Description	|Example
|---------|-------------|------
|get	|Reads a value	|get mykey
|set	|Set a key unconditionally	|set mykey 0 60 5
|add	|Add a new key	|add newkey 0 60 5
|replace	|Overwrite existing key	|replace key 0 60 5
|append	|Append data to existing key	|append key 0 60 15
|prepend	|Prepend data to existing key	|prepend key 0 60 15
|incr	|Increments numerical key value by given number |incr mykey 2
|decr	|Decrements numerical key value by given number |decr mykey 5
|delete	|Deletes an existing key	|delete mykey
|flush_all	|Invalidate specific items immediately |flush_all
|flush_all	|Invalidate all items in n seconds |flush_all 900 
|stats	|Prints general statistics	|stats
|stats	|Prints memory statistics	|stats slabs
|stats	|Prints memory statistics	|stats malloc
|stats	|Print higher level allocation statistics|stats items
|stats	|	|stats detail
|stats	|	|stats sizes
|stats	|Resets statistics	|stats reset
|version	|Prints server version. 	|version
|verbosity	|Increases log level	|verbosity
|quit	|Terminate telnet session	|quit



