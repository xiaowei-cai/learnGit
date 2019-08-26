This is README.

Git is a version control system.
Git is free software.

===========================================================
git init

git add .

git status

git config --global user.name ""

git config --global user.email ""

git commit -m ""

git diff <filename>

git diff HEAD -- <filename> 查看工作区和版本库里面指定文件最新版本的区别

git log --pretty=oneline

git log --graph --pretty=oneline --abbrev-commit
--graph可以看到分支合并图，--abbrev-commit 仅显示 SHA-1 的前几个字符,而非所有的 40 个字符

git branch 列出所有分支，当前分支前面会标一个*号

git branch <branch name>   创建分支

git checkout <branch name> 切换分支

git checkout -b <branch name> 创建分支然后并切换到新创建的分支上

git merge <name> 合并某分支到当前分支（在master上合并分支代码）

git merge --no-ff -m "提交注释" <branch name>
通常，合并分支时，如果可能，Git会用Fast forward模式，但这种模式下，删除分支后，会丢掉分支信息。
如果要强制禁用Fast forward模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

git branch -d <name> 删除分支

git checkout -- <filename> 命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令
一种是要撤销的文件自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
一种是要撤销的文件已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
总之，就是让这个文件回到最近一次git commit或git add时的状态。

git reset --hard HEAD^ (在Git中，用HEAD表示当前版本，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。)

git reset --hard commit_id

git reset HEAD <file>  可以把暂存区的修改撤销掉（unstage），重新放回工作区

git remote -v  查看远程仓库信息，-v表示详细信息，远程仓库默认叫origin

git remote add origin https://github.com/xiaowei-cai/learnGit.git
远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。

git push -u origin master   我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令，后续修改了只要使用git push origin master就可以提交了

git rm <filename>

ssh-keygen -t rsa -C "youremail@example.com" 
生成在/root/.ssh目录，id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，id_rsa.pub是公钥
将公钥添加到github设置里，避免每次提交时校验GitHub用户名和密码，添加SSH Key

git clone git@github.com:xiaowei-cai/learnGit.git
git clone https://github.com/xiaowei-cai/learnGit.git
你也许还注意到，GitHub给出的地址不止一个，还可以用https这样的地址。实际上，Git支持多种协议，默认的git://使用ssh，但也可以使用https等其他协议。
使用https除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，但是在某些只开放http端口的公司内部就无法使用ssh协议而只能用https。

git stash
git stash pop
git cherry-pick <commit>
修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；
当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场；
在master分支上修复的bug，想要合并到当前dev分支，可以用git cherry-pick <commit>命令，把bug提交的修改“复制”到当前分支，避免重复劳动。


git tag v1.0          给分支打上v1.0标签
git tag v1.0 34efds2  给指定commit id打标签
git tag               查看所有标签
git show <tagname>    查看标签信息
git tag -d v1.0       如果标签打错了可以删除，因为创建的标签都只存储在本地，不会自动推送到远程。所以，打错的标签可以在本地安全删除。

git push origin <tagname>推送某个标签到远程
git push origin --tags   一次性推送全部尚未推送到远程的本地标签

删除已经推送远程仓库的标签：先删本地再删远程
git tag -d <tagname>                  可以删除一个本地标签；
git push origin :refs/tags/<tagname>  可以删除一个远程标签


多人协作的工作模式通常是这样：
首先，可以试图用git push origin <branch-name>推送自己的修改；
如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
如果合并有冲突，则解决冲突，并在本地提交；
没有冲突或者解决掉冲突后，再用git push origin <branch-name>推送就能成功！
如果git pull提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream-to <branch-name> origin/<branch-name>。

