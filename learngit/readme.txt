Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes.
Creating a new branch is quick.
this line is fixed conflict dev and master

fix bug 101

git命令：
//初始化
git init

//仓库当前的状态
git status

//差分修改内容
git diff filename

//增加或修改文件
git add readme.txt
git commit -m "修改备注说明"

//查看历史纪录
git log
//查看历史纪录--简易
git log --pretty=oneline

//回退到某一版本，HEAD表示当前版本，HEAD^上一版本，HEAD~100上一百个版本
git reset --hard HEAD^

//根据版本ID回退，不需要输入全部ID，只需要前几位能区分就可以
git reset --hard 3628164

//记录每一次命令
git reflog

//丢弃工作区的修改，checkout是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
git checkout -- filename

//把暂存区的修改撤销掉（unstage），重新放回工作区；  之后再继续用git checkout -- filename 撤销工作区的修改。
git reset HEAD file

//删除版本库中的文件
git rm filename
git commit -m "remove filename"

//github网站 注册建立库
https://github.com/610txc/learngit.git

//关联一个远程库
git remote add origin https://github.com/610txc/learngit.git
git remote add origin git@github.com:610txc/learngit.git

//第一次把本地库的内容推送到远程 
git push -u origin master

//以后每次本地库做了提交，就可以把本地master分支的最新修改推送至GitHub
git push origin master

//删除远程名称
git remote remove origin

//从远程库克隆一个本地库，会在本地当前目录下建立一个gitskills目录
git clone https://github.com/610txc/gitskills.git

//创建dev分支，然后切换到dev分支
git checkout -b dev
//相当于下面两条命令
git branch dev
git checkout dev

//查看当前分支
git branch

//切回到master分支
git checkout master

//把dev分支的工作成果合并到master分支上
git merge dev

//删除dev 分支
git branch -d dev

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

//分支合并冲突时，Git用<<<<<<<，=======，>>>>>>>标记出不同分支的内容，我们修改如下后保存，再提交即可 add ，commit

//用带参数的git log也可以看到分支的合并情况
git log --graph --pretty=oneline --abbrev-commit

//分支合并时候，git会默认用Fast forward模式，但这种模式下，删除分支后，会丢掉分支信息
//如果要强制禁用Fast forward模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息

//准备合并dev分支，请注意--no-ff参数，表示禁用Fast forward
git merge --no-ff -m "merge with no-ff" dev

//Git还提供了一个stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作
git stash

//查看“储藏”起来的当前工作现场
git stash list

//两种恢复办法：
//一是恢复后，stash内容并不删除
git stash apply
//一是恢复后，stash内容删除
git stash drop

//可以多次stash，恢复的时候，先用git stash list查看，然后恢复指定的stash，用命令
git stash apply stash@{0}


https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001376026233004c47f22a16d1f4fa289ce45f14bbc8f11000
//开发一个新feature，最好新建一个分支；
//如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除
git branch -D <branchname>

//查看远程库的信息，
git remote
//查看远程库的详细信息，包括抓取和推送的地址
git remote -v

//各个分支使用建议：
master分支是主分支，因此要时刻与远程同步；
dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

//你的小伙伴要在dev分支上开发，就必须创建远程origin的dev分支到本地，于是他用这个命令创建本地dev分支：
git checkout -b dev origin/dev
//他就可以在dev上继续修改，然后，时不时地把dev分支push到远程：
git commit -m "add 。。。"
git push origin dev

//小伙伴提交后，我再推送dev失败，因为你的小伙伴的最新提交和你试图推送的提交有冲突，解决办法也很简单，
//Git已经提示我们，先用git pull把最新的提交从origin/dev抓下来，然后，在本地合并，解决冲突，再推送
git pull

//如果git pull也失败（no tracking information）了，原因是没有指定本地dev分支与远程origin/dev分支的链接，根据提示，设置dev和origin/dev的链接：
git branch --set-upstream dev origin/dev

//git pull成功，但是合并有冲突，需要手动解决，解决的方法和分支管理中的解决冲突完全一样。解决后，提交，再push：

git commit -m "merge conflict with other person"
git push origin dev
git push origin master

//标签虽然是版本库的快照，但其实它就是指向某个commit的指针（跟分支很像,但是分支可以移动，标签不能移动）
//首先切换到需要打标签的分支上
git branch
git checkout master
git tag v1.0

//查看所有标签
git tag

//默认标签是打在最新提交的commit上的。有时候，如果忘了打标签，比如，现在已经是周五了，但应该在周一打的标签没有打，怎么办？
//方法是找到历史提交的commit id，然后打上就可以了：
git log --pretty=oneline --abbrev-commit
git tag v0.9 6224937

//创建带有说明的标签，用-a指定标签名，-m指定说明文字：
git tag -a v0.1 -m "version 0.1 released" 3628164

//还可以通过-s用私钥签名一个标签：
git tag -s v0.2 -m "signed version 0.2 released" fec145a

//签名采用PGP签名，因此，必须首先安装gpg（GnuPG），如果没有找到gpg，或者没有gpg密钥对，就会报错：
gpg: signing failed: secret key not available
error: gpg failed to sign the data
error: unable to sign the tag
//如果报错，请参考GnuPG帮助文档配置Key

//删除标签
git tag -d v0.1

//标签是建立在本地的，推送某个标签到远程，使用命令
git push origin <tagname>

//一次性推送全部尚未推送到远程的本地标签
git push origin --tags

//标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除，再从远程删除
git tag -d v0.9
git push origin :refs/tags/v0.9

