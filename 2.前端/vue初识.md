## 什么是js？
脚本语言，解释执行
## js运行环境
浏览器引擎，比如chrome v8引擎

## node.js
一款采用chrome引擎的js解释器,但解释执行性能更优，因此可以采用node.js部署后端应用;
可以跟后端的java做个类比，jvm用来运行编译后的字节码，而node.js用来解释执行js脚本代码；

## npm
node package manager,即node包管理器;它是基于node.js环境运行的;
同样可以跟java后端做个类比，maven管理java开源包，而npm管理开源的前端组件;

#### package为什么需要管理?
为了提高软件复用性，提高生产效率，我们会把具备某一功能的代码，封装成一个一个的package或者组件，并把它开源出去，供其他人使用；
如果没有管理器，我们需要自己挨个下载项目依赖的package代码，并把它放到我们的工程中来；当我们依赖的package比较多时，手动添加依赖是非常麻烦的，而npm可以帮我们来管理这些东西;

#### npm安装
- 安装node.js
mac下安装node.js可以采用brew安装;brew命令类似于linux下yum

```
//安装brew，一般mac自带
curl -LsSf http://github.com/mxcl/homebrew/tarball/master |sudo tar xvz -C/usr/local

//安装node.js
brew install node

node -v //查看node.js版本
npm -v  //查看npm版本
```
#### 安装npm开源镜像
npm同样需要有开源的镜像库，不然我需要的package或组件从哪里下载了？
比如taobao开源镜像库
```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```
#### npm命令
```
npm install <package_name>
```
执行此命令，安装对应的package

## vue
前端开发框架
## webstorm
前端开发ide，其他还有vscode等
