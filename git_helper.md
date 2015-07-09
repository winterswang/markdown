git helper
============

#### git 简介 #####

> git是由linus开发的一套分布式版本控制系统，开发的背景是因为linux内核的版本控制工具BitKeeper被收回使用权，大神一怒之下就自己开发了。
其特点主要有：速度快，设计简单，对非线性开发的支持更强力（支持上千个分支），完全分布式，可以高效管理大型项目。

#### git 常用命令大全 ####

- 从远程仓库上拉取代码并在本地创建克隆分支  git clone ****.git   支持https & ssh 两种
- 简单的本地提交新代码  git status(查看仓库状态) / git add xxxx（添加文件到git仓库）  / git commit -m 'commit words'（提交+备注） 
- 从git仓库中删除和还原代码  git rm xxx  / git checkout / git reset 
- 创建分支，切换分支，删除分支，合并分支  git branch xxxx / git checkout xxxx /git branch -d xxxxx / git merge xxxx
- 从远程仓库更新合并代码 git pull origin(默认仓库) master(分支) 
- 将本地代码推送到远程仓库 git push origin(默认仓库) xxxx:yyyy 本地分支名：远程仓库分支名


#### git 分支管理策略 ####
虽然git是去中心化的，纯分布式的版本控制工具。但在项目开发中，依然需要借鉴传统的中心化管理策略。在整个开发过程中，共有两个主要分支：master分支，develop分支。master分之是用来发布大版本的，develop分支日常开发的主分支。此外还有一些辅助性分支，包括：特性分支（新增特性）发布分支（小版本的发布）热补丁分支（及时相应线上bug）

#### git 分支开发流程 ####

- 创建特性分支（特性名可以随意一些）
- 合并到develop分支（特性开发完成，测试通过）
- 待所有特性合并完成，从develop分支拉取，创建release分支（发布分支）
- 如果当前release测试出新的bug,该bug的解决也是从该分支拉取新的分支，然后解决bug，合并到当前分支下。
- 带该release分支稳定后，既可以将该release分支合并到master分支，并对master分支打标签
- 最后，将master的分支代码合并到develop分支上，可以将release解决的bug，在develop分支上直接修复了。


