`master`：默认开发分支
`origin`：默认远程版本库
`Head`：默认开发分支
`Head^`：Head的父提交

# 创建版本库
```
$ git clone <url> # 克隆远程版本库
$ git init        # 初始化本地版本库
```

# 修改和提交
```
$ git status                     # 查看状态
$ git diff                       # 查看变更内容
$ git add .                      # 跟踪所有改动过的文件
$ git add <file>                 # 跟踪指定的文件
$ git mv <old> <new>             # 文件更名
$ git rm <file>                  # 删除文件
$ git rm --cached <file>         # 停止跟踪文件但不删除
$ git commit -m "commit message" # 提交所有更新过的文件
$ git commit --amend             # 修改最后一次提交
$ git stash                      # 临时储藏工作到stash
$ git stash list                 # 查看stash内容
$ git stash apply                # 恢复stash内容
$ git stash drop                 # 删除stash内容
$ git stash pop                  # 恢复并删除stash内容
```

## 查看提交历史
```
$ git log                                          # 查看提交历史，确定回退版本
$ git reflog                                       # 查看命令历史，确定未来版本
$ git log -p <file>                                # 查看指定文件的提交历史
$ git blame <file>                                 # 以列表方式查看指定文件的提交历史
$ git log --graph                                  # 查看分支合并图
$ git log --graph --pretty=oneline --abbrev-commit # 以行方式查看分支合并图
```

## 撤销
```
$ git reset --hard HEAD      # 撤销工作目录中所有的未提交
$ git checkout HEAD <file>   # 撤销指定的未提交文件的修改内容
$ git checkout --file        # 直接撤销指定文件的修改内容
$ git revert <commit>        # 撤销指定的提交
$ git reset --hard commit_id # 回到指定版本
$ 
```

## 分支与标签
```
$ git branch                            # 显示所有本地分支
$ git checkout <branch/tag>             # 切换到指定的分支或标签
$ git branch <new-branch>               # 创建新分支
$ git branch -b <new-branch>            # 创建并切换到新分支
$ git branch -d <branch>                # 删除本地分支
$ git branch -D <branch>                # 强行删除本地分支
$ git tag                               # 列出所有本地标签
$ git tag <tagname>                     # 基于最新提交创建标签
$ git tag -a <tagname> -m "tag message" # 指定标签信息
$ git tag -d <tagname>                  # 删除标签
```

## 合并与衍合
```
$ git merge <branch>                            # 合并指定分支到当前分支
$ git merge --no-ff -m "merge message" <branch> # 使用普通模式合并指定分支到当前分支，合并后有分支合并历史记录
$ git rebase <branch>                           # 衍合指定分支到当前分支
```

## 远程操作
```
$ git remote -v                                            # 查看远程版本库信息
$ git remote show <remote>                                 # 查看指定远程库信息
$ git remote add <remote> <url>                            # 添加远程版本库
$ git fetch <remote>                                       # 从远程库获取代码
$ git pull <remote> <branch>                               # 下载代码并快速合并
$ git push <remote> <branch>                               # 上传代码并快速合并
$ git push -u <remote> <branch>                            # 第一次上传代码并快速合并
$ git checkout -b branch-name origin/branch-name           # 在本地创建和远程分支对应的分支(名称最好一致)
$ git branch --set-upstream branch-name origin/branch-name # 建立本地分支和远程分支的关联
$ git push <remote> : <branch/tagname>                     # 删除远程分支或标签
$ git push --tags                                          # 上传所有标签
$ git push origin <tagname>                                # 推送一个本地标签
$ git push origin --tags                                   # 推送全部未推送过的本地标签
```
