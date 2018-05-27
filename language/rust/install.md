## RUST 


### 安装rust 

#### 在 Unix 类系统如 Linux 和 macOS 上，你只需打开终端并输入：

```
 curl https://sh.rustup.rs -sSf | sh
```

#### 安装完 Rust 以后，我们可以打开 shell，并输入：

```
  rustc --version
  cargo --version
```


### 配置环境变量

设置安装路径。默认它会把Rust装到你的~/.rustup 里，依赖库下载到~/.cargo 里。需要修改的话，设置环境变量RUSTUP_HOME 和 CARGO_HOME 分别修改这两个值。

##### RUSTUP_HOME 和 CARGO_HOME

RUSTUP_HOME 所指向的目录会存放 toolchain 等各种工具。      
CARGO_HOME 所指向的目录只放少量的文件，例如 rustc 等 bin 文件    
```
export CARGO_HOME=$HOME/.cargo
export PATH=$CARGO_HOME/bin:$PATH
export RUSTUP_HOME=$HOME/.rustup
export RUST_SRC_PATH=$RUSTUP_HOME/toolchains/nightly-x86_64-apple-darwin/src
```

### 安装 Rust Language Server

#### 安装 Rustfmt 
```
 cargo +nightly install rustfmt
```

####  nightly 的工具链   
```
rustup toolchain install nightly-x86_64-apple-darwin
```

####  Rust 源码   
```
rustup component add rust-src --toolchain nightly
```


#### 安装 Racer  
```
cargo +nightly install racer
```


#### 安装 rls  
```
rustup component add rls-preview --toolchain nightly
rustup component add rust-analysis --toolchain nightly
```


##### 代理

配置代理#1：国内有些地区访问Rustup的服务器不太顺畅，可以配置中科大的Rustup镜像：设置环境变量

详情链接:http://mirrors.ustc.edu.cn/help/rust-static.html
 
```
RUSTUP_DIST_SERVER=http://mirrors.ustc.edu.cn/rust-static
RUSTUP_UPDATE_ROOT=http://mirrors.ustc.edu.cn/rust-static/rustup
```

配置代理#2：国内有些地方连访问github都不太顺畅，那么你编译软件下载依赖的时候会卡住。这个时候可以设置cargo用的镜像：在你的CARGO_HOME目录下(默认是~/.cargo)建立一个名叫config没有扩展名【切记，没有扩展名！】的文件，内容如下： 
详情链接:http://mirrors.ustc.edu.cn/help/rust-crates.html
 
```
[source.crates-io]
registry = "https://github.com/rust-lang/crates.io-index"
replace-with = 'ustc'
[source.ustc]
registry = "git://mirrors.ustc.edu.cn/crates.io-index"
```
 
 （有人的网络环境受限，没有办法以git协议访问外网，请把上一行里的git://换成https://或者http://）
 

