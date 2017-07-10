http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000


GitHub用户信息 renwg rwg123456

1、windows平台下载地址
   http://msysgit.github.io/

2、安装完成后，还需要最后一步设置，在命令行输入：
   $ git config --global user.name "trumol"
   $ git config --global user.email "475609041@qq.com"

   //因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。
   //git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，

3、创建版本库
   3.1 第一步，选择一个合适的地方，创建一个空目录：
   $ mkdir E:/repository
   $ cd E:/repository
   $ pwd
    E/repository

   3.2 第二步，通过git init命令把这个目录变成Git可以管理的仓库：
   $ git init

4、把一个文件放到Git仓库只需要两步。
   4.1 第一步，用命令git add告诉Git，把文件添加到仓库：
   $ git add readme.txt

   4.2 第二步，用命令git commit告诉Git，把文件提交到仓库：
   $ git commit -m "wrote a readme file"

5、运行git status命令看看结果

6、查看历史记录
   在Git中，我们用git log命令查看：
   $ git log --pretty=oneline

7、版本回退
   我们要把当前版本“append GPL”回退到上一个版本“add distributed”，就可以使用git reset命令：
   在Git中，用HEAD表示当前版本,
   上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100
   $ git reset --hard HEAD^

8、恢复到指定版本 git reset --hard commit_id
   $ git reset --hard cb926e7

9、用git reflog查看命令历史，以便确定要回到未来的哪个版本。
   $ git reflog

10、用git log可以查看提交历史，以便确定要回退到哪个版本。
   $ git log --pretty=oneline

11、撤销修改 git checkout -- file
   $ git checkout -- readme.txt

12、删除，命令git rm用于删除一个文件
   $ git rm readme.txt

13、远程仓库
   第1步：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：
   $ ssh-keygen -t rsa -C "475609041@qq.com"
   点击回车及OK，如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

   第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：
   然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容。

   为什么GitHub需要SSH Key呢？因为GitHub需要识别出你推送的提交确实是你推送的，而不是别人冒充的，而Git支持SSH协议，所以，GitHub只要知道了你的公钥，就可以确认只有你自己才能推送。
	当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。
	最后友情提示，在GitHub上免费托管的Git仓库，任何人都可以看到喔（但只有你自己才能改）。所以，不要把敏感信息放进去。
	如果你不想让别人看到Git库，有两个办法，一个是交点保护费，让GitHub把公开的仓库变成私有的，这样别人就看不见了（不可读更不可写）。另一个办法是自己动手，搭一个Git服务器，因为是你自己的Git服务器，所以别人也是看不见的。这个方法我们后面会讲到的，相当简单，公司内部开发必备。
	确保你拥有一个GitHub账号后，我们就即将开始远程仓库的学习。

14、添加远程仓库
    要关联一个远程库，使用命令
    git remote add origin git@server-name:path/repo-name.git；

    关联后，使用命令,第一次推送master分支的所有内容
    git push -u origin master

    此后，每次本地提交后，只要有必要，就可以使用命令推送最新修改；
    git push origin master

    你已经在本地创建了一个Git仓库后，又想在GitHub创建一个Git仓库，并且让这两个仓库进行远程同步，这样，GitHub上的仓库既可以作为备份，又可以让其他人通过该仓库来协作，真是一举多得。
    第一步，登陆GitHub，然后，在右上角找到“Create a new repo”按钮，创建一个新的仓库：
    在Repository name填入trumol，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库：
    目前，在GitHub上的这个trumol仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

    现在，我们根据GitHub的提示，在本地的learngit仓库下运行命令：
    $ git remote add origin git@github.com:renwg/trumol.git

    请千万注意，把上面的michaelliao替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。
    添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。

    第二步，把本地库的所有内容推送到远程库上：
    $ git push -u origin master

15、从远程库克隆
    使用git clone命令克隆，例如：https://github.com/twbs/bootstrap
    $ git clone git@github.com:twbs/bootstrap.git

16、创建与合并分支

     查看分支：git branch
     创建分支：git branch <name>
     切换分支：git checkout <name>
     创建+切换分支：git checkout -b <name>
     合并某分支到当前分支：git merge <name>
     删除分支：git branch -d <name>

     第一步，我们创建dev分支，然后切换到dev分支(-b参数表示创建并切换)：
     $ git checkout -b dev

     第二步：
     $ git add readme.txt 
     $ git commit -m "branch test"

     第三步：切换回master分支
     $ git checkout master

     切换回master分支后，再查看一个readme.txt文件，刚才添加的内容不见了！因为那个提交是在dev分支上，而master分支此刻的提交点并没有变。

     第四步：把dev分支的工作成果合并到master分支上
     $ git merge dev

     第五步：合并完成后，就可以放心地删除dev分支了
     $ git branch -d dev

17、多人协作
     多人协作的工作模式通常是这样：

     第一步,先更新:
     $ git pull

     第二步,提交:
     $ git push origin branch-name

     注意：
     如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令
     $ git branch --set-upstream branch-name origin/branch-name

     查看远程库信息，使用
     $ git remote -v

     在本地创建和远程分支对应的分支，使用
     $ git checkout -b branch-name origin/branch-name


https://github.com/twbs/bootstrap
http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001375840202368c74be33fbd884e71b570f2cc3c0d1dcf000
  
