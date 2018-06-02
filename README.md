### Git 学习笔记

* 1.git init 初始化本地仓库
* 2.git add * 添加文件到仓库
* 3.git commit -m "描述说明" 提交到仓库
* 4.git status 查看版本状态     innsertios 插入
* 5.git diff 查看上次修改
* 6.git add * 再次添加到版本库 我就记住啦~

* 7.git log 命令显示从最近到最远的提交日志  [head 表示当前版本]


### 时光穿梭机

* 8.git reset --hard HEAD^ 回退到上一个版本  可以用git log 查看下日志

* 9.git reset --hard 提交名(前7位) 可以返回当前版本  注意： 在命令行窗口没关的情况下

Git的版本回退速度非常快，因为Git在内部有个指向当前版本的HEAD指针，当你回退版本的时候，Git仅仅是把HEAD从指向append GPL：  

关键在于 commit id

不小心把命令行窗口关了怎么办?

git还是可以补救的：

* 10.git reflog 记录每一次的命令 它会告诉你 “穿梭的时空变化”


工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。

Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。

我们写文件的地方叫工作区           提交的地方叫版本库（.git它是被隐藏的）    版本库： 1.暂存区     2.master分支


* git add 操作是将我们所有的修改提交到暂存区  然后git commit一次性提交到master 每次提交都有一个commit id

* 提交后工作区如果没有做修改 那么它会是干净的

***** 暂存区 一定要理解 ！！！！！！ Git做的是版本管理的修改 而非文件******

git add * 是把文件修改提交到 暂存区    如果一个文件修改了 并没有git add  直接commit是没法把修改提交上的

git commit 是一次性将 暂存区的修改 提交到 master



用git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别




### 撤销修改

* git checkout -- .file  撤销工作区的修改

1.一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

2.一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

当然 git reset 也可以帮我们回到之前的修改

git reset HEAD 可以把暂存区的修改撤销掉（unstage）重新放回工作区：  就是丢弃暂存区的修改

注意不要和git reset --hard commit_id 混淆   它是用来做版本替换


### 删除操作

* 1.rm  直接删掉工作区的文件
* 2.git rm filename 删掉版本库的文件

当工作区的文件被删除后  可以用git reset --hard 从版本库中恢复该文件

当然我们可以撤销工作区的修改 也可以一键恢复我们的文件 当然在版本库没有被删除的情况下 也就是没有commit的情况下


如果执行git rm 则工作区和版本库都会被删除掉   注意：做了修改后要 commit 提交到master分支 

























