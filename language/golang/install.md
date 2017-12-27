#### golang安装

##### 1.准备文件   

> Mac平台准备 go1.9.2.darwin-amd64.tar.gz
> 
> Linux平台 go1.9.2.linux-amd64.tar.gz


##### 2.安装   

```
	sudo cp ./go*.tar.gz  /usr/local
	
	cd /usr/local
	
	# 如果没有安装tar 
	# mac : brew install tar 
	# ubuntu : apt-get install tar
	# Fedora : yum install tar  / dnf install tar
	sudo tar -zxvf go*.tar.gz

```
这个时候已经可以看到在"/usr/local" 有go的一个目录了

检验golang版本

```    
	cd /usr/local/go/bin
	
	./go -version  

```    

 提示内容如下 说明golang安装包正常      
           
```          
 	 
	 flag provided but not defined: -version
	Go is a tool for managing Go source code.
	
	Usage:
	
		go command [arguments]
	
	The commands are:
	
		build       compile packages and dependencies
		clean       remove object files
		doc         show documentation for package or symbol
		env         print Go environment information
		bug         start a bug report
		fix         run go tool fix on packages
		fmt         run gofmt on package sources
		generate    generate Go files by processing source
		get         download and install packages and dependencies
		install     compile and install packages and dependencies
		list        list packages
		run         compile and run Go program
		test        test packages
		tool        run specified go tool
		version     print Go version
		vet         run go tool vet on packages
	
	Use "go help [command]" for more information about a command.
	
	Additional help topics:
	
		c           calling between Go and C
		buildmode   description of build modes
		filetype    file types
		gopath      GOPATH environment variable
		environment environment variables
		importpath  import path syntax
		packages    description of package lists
		testflag    description of testing flags
		testfunc    description of testing functions
	
	Use "go help [topic]" for more information about that topic.   


```
创建GOPATH目录


```
> cd $HOME
> mkdir gopath

```

配置环境变量

```    
sudo vim /etc/profile
```  
在文件末尾增加上下边三行，保存并退出. 

```
	export GOROOT=/usr/local/go
	export GOPATH=$HOME/gopath
	export PATH=$GOROOT/bin:$GOPATH/bin:$PATH

```

环境变量立即生效

```
> source /etc/profile

```

#### 扩展 - Go环境变量

> $GOROOT 表示 Go 在你的电脑上的安装位置，它的值一般都是$HOME/go，当然，你也可以安装在别的地方。    


> $GOPATH 默认采用和$GOROOT一样的值，但从 Go 1.1 版本开始，你必须修改为其它路径。它可以包含多个包含 Go 语言源码文件、包文件和可执行文件的路径，而这些路径下又必须分别包含三个规定的目录：src、pkg和bin，这三个目录分别用于存放源码文件、包文件和可执行文件。    

> $GOARM 专门针对基于 arm 架构的处理器，它的值可以是 5 或 6，默认为 6。    
 
> $GOMAXPROCS 用于设置应用程序可使用的处理器个数与核数
 
> $GOARCH 表示目标机器的处理器架构，它的值可以是 386、amd64 或 arm。
 
> $GOOS 表示目标机器的操作系统，它的值可以是 darwin、freebsd、linux 或 windows。
 
> $GOBIN 表示编译器和链接器的安装位置，默认是$GOROOT/bin，如果你使用的是 Go 1.0.3 及以后的版本，一般情况下你可以将它的值设置为空，Go 将会使用前面提到的默认值。
> 
> 
 
##### golang支持跨平台编译    
如:在其他平台上编译Linux平台运行的包

先设置环境变量,设置完毕之后就可以,跨平台编译了      

```   
export GOARCH=amd64  
export GOOS=linux  

```   
