- 学习过程记录
- DONE 2025-02-12 记录
  SCHEDULED: <2025-02-12 Wed>
  DEADLINE: <2025-02-12 Wed>
  collapsed:: true
  :LOGBOOK:
  CLOCK: [2025-02-12 Wed 10:39:00]--[2025-02-12 Wed 12:08:00] =>  01:29:00
  :END:
  :AGENDA:
  estimated: 1h30m
  :END:
	- 一、Git 基础
		- 01 课程综述
		- 02 安装 Git
		  collapsed:: true
			- https://git-scm.com/book/zh/v2/起步-安装-Git
			- ```
			  git --version # 返回 git 版本
			  ```
			- [将 macOS 的自带 Git 换到 homebrew 安装的 Git](((67afff81-317f-4bf4-bc09-665b0d44d4e6)))
		- 03 使用 Git 之前需要做的最小配置
		  collapsed:: true
			- 配置 user.name 和 user.email
			  ```
			  git config --global user.name 'your_name'
			  git config --global user.email 'your_email@domain.com'
			  
			  #还可以设置 local 域下的名称和邮箱
			  
			  git config --list #查看设置
			  ```
		- 04 创建第一个仓库并配置 local 用户信息
		  collapsed:: true
			- 本节提及的 git 命令
			  ```
			  git init #创建项目文件夹
			  git add #增加文件
			  git commit #建立一次提交
			  git status #查看状态
			  git log #查看日志
			  ```
			- 进一步学习 `cd` 命令
			  collapsed:: true
				- `..` 可以返回上一级目录
			- `pwd` 显示当前路径
			- `ls -al` 显示当前路径下的所有文件
			- 进一步学习 `cp` 拷贝命令
				- 拷贝文件夹时用 `cp -r`
		- 05 通过几次 commit 来认识工作区和暂存区
		  collapsed:: true
			- 本节提及的 git 命令
			  ```
			  git add -u #将已被git管理的文件一起提交到暂存区，u代表update
			  ```
			- `mkdir` 创建目录
			- `vi` 打开文件
		- 06 给文件重命名的简便方法
		  collapsed:: true
			- 本节提及的 git 命令
			  ```
			  git rm #移除文件
			  git mv #重命名文件
			  git reset --hard #用的时候需要注意，暂存区所有的变更都会被清理掉
			                         📝我在创建分支的时候因为分知名错误，误使用了这个命令，造成创建分支后的commit信息都被清空了，于是我开始重新打造仓库。2025-02-17 17:41:34
			  ```
			- `mv` 移动或重命名文件
		- 07 通过 git log 查看版本演变历史
			- 本节提到的 git 命令
			  ```
			  git log #什么参数都不加的话，指向的是当前分支，查看当前分支的历史信息
			  git log --all #显示所有分支
			  git log --all --graph #图形化显示所有分支
			  git log 分支名 #显示指定分支
			  
			  git log --oneline #简洁显示
			  git log -n4 # 显示最近的 4 条，想显示最近的几条，就把数字改成几
			  #以上两个命令也可以组合，如`git log -n4 --oneline`
			  
			  git branch -v #查看本地有多少分支
			  git branch -av #查看有多少分支
			  git checkout -b <分支名> <某个分支/某个commit> #从某个分支或者commit创建新分支并切换到这个分支
			  git commit -am #把工作区的内容直接创建到版本库
			  ```
- DONE 2025-02-19 记录
  SCHEDULED: <2025-02-19 Wed>
  collapsed:: true
  :LOGBOOK:
  CLOCK: [2025-02-19 Wed 16:58:00]--[2025-02-19 Wed 17:06:00] =>  00:08:00
  CLOCK: [2025-02-19 Wed 17:22:00]--[2025-02-19 Wed 18:16:00] =>  00:54:00
  CLOCK: [2025-02-19 Wed 21:52:00]--[2025-02-19 Wed 22:18:00] =>  00:26:00
  :END:
	- 一、Git 基础
		- 08 gitk：通过图形界面工具来查看版本历史
		  collapsed:: true
			- `zsh: command not found: gitk`，为 macOS 安装 gitk
			  ```
			  brew install git # 更新 git
			  brew install git-gui  # 安装 gitk
			  ```
			  ℹ️ [zsh: command not found: gitk-CSDN博客](https://blog.csdn.net/hanxiaoyang6/article/details/129960534)
		- 09 探秘 .git 目录
		  collapsed:: true
			- 本节提到的 git 命令
			  ```
			  git branch -av # 查看有多少分支
			  git checkout 分支名 # 切换分支命令
			  git cat-file -t # 看文件类型（tree、blob、commit）
			  git cat-file -p # 看文件内容
			  ```
			- `.git` 文件夹下的内容
				- `HEAD` 文件表示整个仓库正在工作在哪个分支上，所以里面是一个引用
				- `.git/refs/heads` 文件夹下的文件（以分支名命名，如 `master`）表示该分支的指针指向哪个 commit
			- `cat` 命令
			- blob 是文件对象
		- 10 commit、tree 和 blob 三个对象之间的关系
			- 一个 commit 对应一个 tree，tree 其实是文件夹树
		- 11 小练习：数一数 tree 的个数
			- `echo` 命令是干什么的？
			- `find` 命令是干什么的？
- DONE 2025-02-20 记录
  SCHEDULED: <2025-02-20 Thu>
  collapsed:: true
  :LOGBOOK:
  CLOCK: [2025-02-20 Thu 17:38:00]--[2025-02-20 Thu 18:28:00] =>  00:50:00
  :END:
	- 一、Git 基础
		- 12 分离头指针情况下的注意事项
			- 本节提到的 git 命令
			  ```
			  git branch -av # 查看有多少分支
			  git checkout 某个commit # 切换到分离头指针状态
			  git checkout 分支名 # 切换分支命令
			  git branch <分支名> <commit值> # 为处于分离头指针状态的 commit 绑定分支
			  gitk --all 
			  ```
			- HEAD 没有指向任何分支，这种情况叫做「分离头指针（detached HEAD）」状态，在做一些尝试性的变更的时候可以使用，如果效果不好可以不再理会它；如果想要保留，就要为它创建一个分支。
			- 在 git 的眼里，如果一个 commit 没有和一个 branch 或 tag 绑定，那这个 commit 就是不重要的，日后都是要被清除的。
		- 13 进一步理解 HEAD 和 branch
		  collapsed:: true
			- 本节提到的 git 命令
			  ```
			  git branch -av # 查看目前有多少分支，分支前面的 * 指示当前处于的分支
			  git checkout -b <新分支名> <某个分支/某个commit> #从某个分支或 commit 创建新分支并切换到这个分支
			  git log -n4 # 显示最近的 4 条，想显示最近的几条，就把数字改成几
			  git diff <commit> <commit> # 比较两个 commit
			  git diff HEAD HEAD^1 # 比较前面两个 HEAD 的不同
			      """
			      git diff HEAD HEAD^ = git diff HEAD HEAD^1 = git diff HEAD HEAD~1
			      git diff HEAD HEAD^^ = git diff HEAD HEAD~2
			      """
			  ```
- DONE 2025-02-23 记录
  collapsed:: true
  SCHEDULED: <2025-02-23 Sun>
  :LOGBOOK:
  CLOCK: [2025-02-23 Sun 10:50:00]--[2025-02-23 Sun 11:11:00] =>  00:21:00
  :END:
	- 二、独自使用 Git 时的常见场景
		- 01 怎么删除不需要的分支
			- 本节提到的 git 命令
			  ```
			  git branch -d <分支名> #删除分支
			  git branch -D <分支名> #删除分支，如果以上的命令告警说分支没有被合并，并且确认风险，那可以使用这个命令将分支删除
			  ```
- LATER 2025-02-24 记录
  SCHEDULED: <2025-02-24 Mon>
  :LOGBOOK:
  CLOCK: [2025-02-24 Mon 22:09:00]--[2025-02-24 Mon 22:35:00] =>  00:26:00
  :END:
	- 二、独自使用 Git 时的常见场景
		- 02 怎么修改最新 commit 的 message？
			- 本节提到的 git 命令
			  ```
			  git commit --amend # 对最近提交的 commit 的 message 进行修改
			  git log -1 # 最近一次提交
			  ```
- LATER 2025-02-26 记录
  SCHEDULED: <2025-02-26 Wed>
  :LOGBOOK:
  CLOCK: [2025-02-26 Wed 17:29:00]--[2025-02-26 Wed 18:13:00] =>  00:44:00
  :END:
	- 二、独自使用 Git 时的常见场景
		- 03 怎么修改老旧 commit 的 message？
			- 本节提到的 git 命令
			  ```
			  git rebase -i <commit> # 变基，commit 要选择想要进行操作的对象的父亲，独自操作时可以这样进行变基，但是对于已提交到团队的分支上，就不能这样轻易的变基了。
			  ```
		- 04 怎样把连续的多个 commit 整理成 1 个？
			- 本节提到的 git 命令
			  ```
			  git rebase -i <commit> # 变基
			  ```
- LATER 2025-03-08 记录
  SCHEDULED: <2025-03-08 Sat>
	- 二、独自使用 Git 时的常见场景
		- 05 怎样把间隔的多个 commit 整理成 1 个？
			- 本节提到的 git  命令
-
- 一些参考资料：
	- [Git教程 - 廖雪峰的官方网站](https://liaoxuefeng.com/books/git/introduction/index.html)