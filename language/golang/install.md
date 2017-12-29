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

#### 各种编译器的插件    
```    
Atom: go-plus https://github.com/joefitzgerald/go-plus  
VS Code: vscode-go https://github.com/Microsoft/vscode-go  
Vim: vim-go https://github.com/fatih/vim-go  
Emacs: go-mode https://github.com/dominikh/go-mode.el  
```   
#### 常用的工具
```
go get -u -v github.com/nsf/gocode
go get -u -v github.com/rogpeppe/godef
go get -u -v github.com/golang/lint/golint
go get -u -v github.com/lukehoban/go-outline
go get -u -v sourcegraph.com/sqs/goreturns
go get -u -v golang.org/x/tools/cmd/gorename
go get -u -v github.com/tpng/gopkgs
go get -u -v github.com/newhook/go-symbols
go get -u -v golang.org/x/tools/cmd/guru
```  
#### go工具集合收录   
```   
go get -u -v github.com/3rf/codecoroner 
go get -u -v github.com/kisielk/errcheck
go get -u -v github.com/lukehoban/go-find-references
go get -u -v github.com/lukehoban/go-outline
go get -u -v github.com/newhook/go-symbols
go get -u -v github.com/nsf/gocode
go get -u -v golang.org/x/tools/cmd/gorename
go get -u -v sourcegraph.com/sqs/goreturns
go get -u -v golang.org/x/tools/cmd/goimports
go get -u -v github.com/rogpeppe/godef
go get -u -v github.com/golang/lint/golint
go get -u -v github.com/tpng/gopkgs
go get -u -v golang.org/x/tools/cmd/guru
go get -u -v github.com/kardianos/govendor
go get -u -v github.com/jstemmer/gotags  
go get -u -v github.com/cweill/gotests/...
go get -u -v github.com/cweill/gotests/gotests
go get -u -v github.com/josharian/impl
go get -u -v github.com/zmb3/gogetdoc
go get -u -v github.com/fzipp/gocyclo
go get -u -v github.com/mvdan/interfacer/cmd/interfacer
go get -u -v github.com/tsenart/deadcode
go get -u -v golang.org/x/tools/cmd/gotype
go get -u -v github.com/client9/misspell
go get -u -v github.com/dominikh/go-tools
go get -u -v github.com/360EntSecGroup-Skylar/goreporter
go get -u -v github.com/fatih/gomodifytags
go get -u -v github.com/alecthomas/gometalinter
go get -u -v github.com/derekparker/delve/cmd/dlv
go get -u -v github.com/golang/protobuf/protoc-gen-go
go get -u -v github.com/gogo/protobuf/protoc-gen-gofast
go get -u -v github.com/smartystreets/goconvey

go get -u -v github.com/golang/mock/gomock
go get -u -v github.com/golang/mock/mockgen  
```   
#### 以上工具的说明     
```

codecoroner  检查死代码
errcheck  错误代码检测
go-find-references  搜索参考引用 
go-outline  文件大纲
go-symbols  工作区符号搜索
gocode  代码自动完成
gorename  重命名
goreturns goimports gofmt 代码格式化
gopkgs 添加引用
godef 快速提示信息/跳转到定义
golint 检测语法问题
guru  实现用gd命令跳转到函数定义
govendor  项目依赖管理
gotags  变量、类型、函数等，并支持跳,类似于ctags

gomock,mockgen,gomock测试
gotests test生成
impl 接口实现 在vim中
gogetdoc 文档
gocyclo 用来检查函数的复杂度。
interfacer 这个工具提供接口类型的建议，换句话说，它会对可以本没有必要定义成具体的类型的代码提出警告
deadcode   会告诉你哪些代码片段根本没用。
gotype  会对go文件和包进行语义(semantic)和句法(syntactic)的分析,这是google提供的一个工具。
misspell  用来拼写检查，对国内英语不太熟练的同学很有帮助。
go-tools 中有一个 staticcheck。 staticcheck是一个超牛的工具，提供了巨多的静态检查
goreporter  代码分析工具
gomodifytags 增加struct的tag
gometalinter并发执行go 工具
dlv  调试工具
protoc-gen-go go protobuf 工具
protoc-gen-gofast gogoprotobuf工具
goconvey awesome的testing工具
```   
#### 新增
```   
go get -u -v github.com/jgautheron/goconst/cmd/goconst goconst 会查找重复的字符串，这些字符串可以抽取成常量。
go get -u -v github.com/dominikh/go-tools/tree/master/simple gosimple 提供信息，帮助你了解哪些代码可以简化。
```  

