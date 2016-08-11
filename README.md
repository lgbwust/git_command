# git_command
git常用操作及应用

第一步：在本机上操作
1、安装 Git 客户端
如何安装不同操作系统的 Git 客户端，参见：http://help.github.com/win-set-up-git/

2、打开 Git Bash，开始键入各种配置信息：

git config --global user.name "You Name"
git config --global user.email yourmail@server.com

这里的配置信息中的用户名和用户邮箱，在后面 GitHub 中会用到，尽力准确配置，不要用 test or test@mail.com 等等的测试数据去配置。


第二步：注册 GitHub，配置相关信息

1、成功注册 GitHub 帐号后，创建 GitHub SSH密匙，Git Bash 下键入命令： 
ssh-keygen -C 'yourmail@server.com' -t rsa

生成密钥的时候使用默认的路径就行了，密码自己设定。 
然后会在 C:User你的windows用户名.ssh 下找到 id_rsa.pub 文件 
笔者操作系统 windows 7 英文版，其他版本的 windows 系统可能路径略有不同。
.ssh 文件夹下同时有 id_rsa 和 id_rsa.pub 文件（注意在开启后缀名的情况下），id_rsa 是置于本地机器的密钥，用于匹配置于服务器端的密钥文件 id_rsa.pub，这样才能建立 SSH 连接。


2、回到 GitHub 个人首页，点击 Account Settings -> SSH Public Keys -> Add another public key。title 可以随便取名字，Key 里面添加的内容为 id_rsa.pub 文件内所有的代码。然后点击 Apply 即可。 
测试与 GitHub 是否连接成功：SSH -v git@github.com


3、可以在 GitHub 上添加第一个 Git 仓库 ，配置项目名称和相关信息。 
如何在 GitHub 上添加 Git 仓库参见： http://help.github.com/create-a-repo/ 

4、在本地创建项目文件，在 Bash 下键入一下代码： 
mkdir test
cd test
git init
touch README
git add README
git commit -m 'first commit'
git remote add origin git@github.com:youusername/test.git
git push -u origin master

推送成功后，就可以在 GitHub 上看到 push 上去的项目文件了。
