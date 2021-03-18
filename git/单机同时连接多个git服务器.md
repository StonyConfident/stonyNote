## 一.闲聊
作为一个developer同学，git使用肯定少不了;
git真的很好使，帮你存代码、帮你存笔记、帮你存一切能存的、帮你做提交记录、等等！

git包括客户端和服务端，git客户端的安装很简单，linux下就一条命令的事;
至于服务端，有开源的github社区(比如github.com),也有公司搭建的git服务器;
那么如何来配置git访问多个服务器呢？

## 二.实战操作
- **1.安装好git客户端后，本地/home/{user}/目录下会新增一个.ssh文件夹,创建config文件，配置信息如下:**

		//公司的git仓库
		Host gitlab.aaaa.com
		User shijian
		HostName  gitlab.aaaa.com
		PreferredAuthentications publickey
		IdentityFile ~/.ssh/id_rsa
		//个人的github仓库
		Host github.com
		User StonyConfident
		HostName github.com
		PreferredAuthentications publickey
		IdentityFile ~/.ssh/id_rsa_stony

- **2.在.ssh目录下创建id_rsa, id_rsa.pub, id_rsa_stony, id_rsa_stony.pub 四个文件，填入公司账号和个人账号的公私钥即可**
关于怎么生成一对公钥和私钥，以及绑定到git服务端，可自行搜索解决;

- **3.在/home/{user}/目录下还会存在一个.gitconfig的文件，里面是配置的开发者信息，包括用户名和邮件等;开发者信息就是代码的annotate信息,可以取一些比较牛x的昵称**

		[user]
		        name = stony
		        email = stony@xxxx.com


- **4.配置好后，就可以使用git clone命名开始下载远程服务端的源代码了**
