#### gofmt
find . -name "*.go" -not -path "./vendor/*" -not -path ".git/*" | xargs gofmt -s -d


#### gocyclo
gocyclo 用来检查函数的复杂度。  
go get -u github.com/fzipp/gocyclo  
gocyclo -over 12 $(ls -d */ | grep -v vendor)   
gocyclo -top 10 $(ls -d */ | grep -v vendor)

#### interfacer
interfacer 是一个有趣的工具，依照作者所说：

这个工具提供接口类型的建议，换句话说，它会对可以本没有必要定义成具体的类型的代码提出警告  
 go get -u github.com/mvdan/interfacer/cmd/interfacer 
interfacer $(glide nv)  


#### deadcode 
deadcode会告诉你哪些代码片段根本没用。  
go get -u github.com/tsenart/deadcode  
find . -type d -not -path "./vendor/*" | xargs deadcode


#### gotype  
gotype会对go文件和包进行语义(semantic)和句法(syntactic)的分析,这是google提供的一个工具。
go get -u golang.org/x/tools/cmd/gotype
find . -name "*.go" -not -path "./vendor/*" -not -path ".git/*" -print0 | xargs -0 gotype -a


#### misspell  
misspell用来拼写检查，对国内英语不太熟练的同学很有帮助。

 go get -u github.com/client9/misspell
find . -type f -not -path "./vendor/*" -print0 | xargs -0 misspell


#### staticcheck  
staticcheck是一个超牛的工具，提供了巨多的静态检查，就像 C#生态圈的 ReSharper 一样。  
 go get -u honnef.co/go/staticcheck/cmd/staticcheck
staticcheck $(glide nv)


#### gosimple  
gosimple 提供信息，帮助你了解哪些代码可以简化。
go get -u honnef.co/go/simple/cmd/gosimple
gosimple $(glide nv)

#### goconst  
goconst 会查找重复的字符串，这些字符串可以抽取成常量。

 go get -u github.com/jgautheron/goconst/cmd/goconst
goconst ./… | grep -v vendor

