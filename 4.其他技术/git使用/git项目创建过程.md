### 远程仓库存在项目
直接使用git clone命令下载即可，本地仓库直接跟远程仓库关联上。

### 若远程仓库不存在，本地项目如何推送至远程
- **1.本地目录初始化**
```
<!-- cd至目标目录 -->
git init
```
- **2.先将本地的文件变更提交至本地仓库**
```
git add .
git commit -m "改动描述"
```
- **3.设置对应的远程仓库**
```
git remote add origin git@github.com:NNN/test.git
```
git@github.com:NNN/test.git 为对应的远程git服务器的repository，并取别名为origin
- **在远程仓库创建对应的项目**
上一步我们设置的远程仓库项目git@github.com:NNN/test.git，必须是已经存在的，否则我们在下一步无法成功提交到远程。
如下图，登陆后直接创建一个名为test的新repository:
![](assets/git项目创建过程-d6fb8cdc.png)

- **推送至远程**
```
git push -u origin master
```
将本地master分支推送至远程git服务器origin，同时指定origin为默认远程服务器(一个本地项目是可以同时对应多个git远程服务器的);
