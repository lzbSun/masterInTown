# git 命令

![git 专有名词](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120901.png)([转自阮一峰博客](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html))

## git专有名词译名
- Workspace: 工作区
- Index/ Stage: 暂存区
- Repository: 仓库区（本地仓库）
- Remote: 远程仓库

## 新建代码库
- git init
- git init [project-name] 新建一个目录，将其初始化为git 代码库
- git clone [url] 下载一个项目和它的整个代码历史

## 配置
- git config --list 显示当前git 配置
- git config -e [--global] 编辑git 配置文件

## 增加、删除文件
- git add [file1] [file2] 添加指定文件的暂存区
- git add [dir] 添加指定目录到暂存区， 包括子目录
- git add . 添加当前目录的所有文件到暂存区
- git add -p 添加每个变化前，都会要求确认 对于同一个文件的多处变化，可以实现分次提交
- git rm [file1] [file2] 删除工作区文件，并且将这次删除放入暂存区
- git rm --cached [file] 停止追踪指定文件， 但该文件会保留在工作区
- git mv [file-original] [file-renamed] 改名文件, 并且将这个改名放入暂存区

## 代码提交
- git commit -m [message] 提交暂存区到仓库区
- git commit [file1] [file2] -m [message] 提交暂存区的指定文件到仓库区
- git commit -a 提交工作区自上次commit之后的变化，直接到仓库区
- git commit -v 提交时显示所有diff信息
- git commit -amend -m [message] 使用一次新的commit 替代上一次提交，如果代码没有任何变化，则用来改写上一次commit的提交信息
- git commit -amend [file1] [file2] 重做上一次commit，并包括指定文件的变化

## 分支
- git branch 列出所有本队分支
- git branch -r 列出所有远程分支
- git branch -a 列出所有远程分支和本地分支
- git branch [branch-name] 新建一个分支，但依然停留在当前分支
- git checkout -b [branch] 新建一个分支，并切换到该分支
- git checkout [branch-name] 切换到指定分支，并更新工作区
- git branch [branch] [commit] 新建一个分支，指向指定commit
- git branch --track [branch] [remote-brach] 新建一个分支，与指定的远程分支建立追踪关系
- git checkout - 切换到上一个
- git branch --set-upstream [branch] [remote-brach] 建立追踪关系，在现有分支与指定的远程分支之间
- git merge [branch] 合并指定分支到当前分支
- git cherry-pick [commit] 选择一个commit ，合并进当前分支
- git branch -d [branch-name] 删除一个分支
- 删除远程分支
  - git push origin --delete [branch-name]
  - git branch -dr [remote-brach]

## 标签
- git tag 列出所有tag
- git tag [tag] 新建一个tag 在当前commit
- git tag -d [tag] 删除本地tag
- git push origin :refs/tags/[tagName] 删除远程tag
- git show [tag] 查看tag信息
- git push [remote] [tag] 提交指定tag
- git push [remote] --tags 提交所有tag
- git checkout -b [branch] [tag] 新建一个分支，指向某个tag

## 查看信息
- git status 显示所有并更文件
- git log 显示当前分支的版本历史
- git log --stat 显示commit 历史， 以及每次commit 发生变更的文件
- git log -S [keyword] 搜索提交历史，根据关键词
- git log [tag] HEAD --pretty=format:%s   显示某个commit之后的所有变动，每个commit占据一行
- git log [tag] HEAD --grep feature 显示某个commit 之后的所有变动，其’提交说明’必须符合搜索条件
- git log --follow [file]     git whatchanged [file] 显示某个文件的版本历史，包括文件改名
- git diff --shortstat "@{0 day ago}" 显示今天你写了多少行代码
- git show [commit] 显示某次提交的元数据和内容变化
- git reflog 显示当前分支的最近几次提交

## 远程同步
- git fetch [remote] 下载远程仓库的所有变动
- git remote -v 显示所有远程仓库
- git remote show [remote]  显示某个远程仓库的信息
