Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes.

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

//

//

//