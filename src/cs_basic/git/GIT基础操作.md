---
title: codecommit 单个文件的限制
date: 2023-10-17 02:59:52
categories: GIT
tags: 
    - GIT
---


### 基础操作：

1. **初始化与克隆**：
    - `git init`: 在当前目录下初始化一个新的 Git 仓库。
    - `git clone [URL]`: 从远程仓库克隆到本地。

2. **查看状态与历史**：
    - `git status`: 显示工作目录和暂存区的状态。
    - `git log`: 查看提交历史。
    - `git log --oneline`: 精简格式的提交历史。
    - `git log -p`: 查看提交历史和每次提交的差异。
    - `git log --graph --oneline --all`: 图形化显示所有分支的提交历史。

3. **添加、提交和删除**：
    - `git add [file-name]`: 将文件的更改添加到暂存区。
    - `git commit -m "Commit message"`: 提交暂存区的更改。
    - `git rm [file]`: 删除文件并暂存这次删除。

4. **分支与合并**：
    - `git branch [new-branch-name]`: 创建新分支。
    - `git checkout [branch-name]`: 切换到指定分支。
    - `git merge [source-branch]`: 合并指定分支到当前分支。
    - `git branch -d [branch-name]`: 安全地删除分支。

5. **远程仓库操作**：
    - `git remote add`: 添加新的远程仓库。
    - `git remote -v`: 查看已配置的远程仓库。
    - `git remote show [remote-name]`: 查看远程仓库的详细信息。
    - `git pull`: 从远程获取并合并到当前分支。
    - `git push`: 推送本地更改到远程仓库。

6. **查看差异**：
    - `git diff`: 查看暂存区和工作目录的差异。
    - `git diff [branch1]..[branch2]`: 查看两个分支之间的差异。

7. **重置和清理**：
    - `git reset [file]`: 从暂存区移除文件，但不修改工作目录。
    - `git clean -f`: 删除未跟踪的文件。

### 高级操作：

1. **交互式操作**：
    - `git add -i`: 交互式地选择要暂存的更改。
    - `git rebase -i [base-commit]`: 交互式地重新设置提交基点。

2. **修改历史**：
    - `git commit --amend`: 修改最后一次提交。
    - `git rebase --onto [newbase] [since] [until]`: 更具选择性地重新应用提交。
    - `git cherry-pick [commit]`: 将指定的提交从一个分支应用到当前分支。

3. **查找问题**：
    - `git bisect`: 二分查找引起问题的提交。
    - `git blame [file]`: 查看文件每一行的最后修改者。

4. **临时保存更改**：
    - `git stash`: 临时保存当前更改。
    - `git stash list`: 查看所有已存储的更改。
    - `git stash apply [stash@{n}]`: 应用指定的存储。
    - `git stash drop [stash@{n}]`: 删除指定的存储。
    - `git stash clear`: 删除所有存储。

5. **配置和别名**：
    - `git config --global color.ui true`: 开启彩色输出。
    - `git config --global alias.[alias-name] '[command]'`: 设置命令别名。

6. **工作目录与子模块**：
    - `git worktree add [path] [branch]`: 同一仓库中的多工作区。
    - `git submodule add [repository-url] [path]`: 将其他仓库作为子模块加入。

7. **历史和引用日志**：
    - `git reflog`: 查看引用日志。

8. **复杂的历史修改**：
    - `git filter-branch`: 修改整个仓库的历史。

9. **安全的强推**：
    - `git push [remote-name] [branch-name] --force-with-lease`: 更安

全地强制推送。

这些命令覆盖了 Git 的许多功能，从基础的日常任务到复杂的仓库操作。使用高级命令时应格外小心，并确保了解它们的含义和后果。