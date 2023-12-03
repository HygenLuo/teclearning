# git基本概念
- 工作区：仓库的目录，工作区是独立于各个分支的。
- 暂存区：数据暂时存放的区域，类似于工作区写入版本前的缓存区。暂存区是独立于各个分支的。
- 版本库：存放所有已经提交到本地仓库的代码版本。
- 版本结构：树结构，树中每个节点代表一个代码版本。
# git常用命令
## 全局设置
1. `git config --global user.name xxx`：设置全局用户名，信息记录在`~/.gitconfig`文件中
2. `git config --global user.email xxx@xxx.com`：设置全局邮箱地址，信息记录在`~/.gitconfig`文件中
3. `git init`：将当前目录配置成git仓库，信息记录在隐藏的.git文件夹中
## 常用命令
1. `git add XX`：将XX文件添加到暂存区
2. `git commit -m "给自己看的备注信息"`：将暂存区的内容提交到当前分支
3. `git status`：查看仓库状态
4. `git log`：查看当前分支的所有版本
5. `git push -u (第一次需要-u以后不需要)`：将当前分支推送到远程仓库
6. `git clone git@git.acwing.com:xxx/XXX.git`：将远程仓库XXX下载到当前目录下
7. `git branch`：查看所有分支和当前所处分支
## 查看命令
1. `git diff XX`：查看XX文件相对于暂存区修改了哪些内容
2. `git status`：查看仓库状态
3. `git log`：查看当前分支的所有版本
4. `git log --pretty=oneline`：用一行来显示
5. `git reflog`：查看HEAD指针的移动历史（包括被回滚的版本）
6. `git branch`：查看所有分支和当前所处分支
7. `git pull`：将远程仓库的当前分支与本地仓库的当前分支合并
## 删除命令
1. `git rm --cached XX`：将文件从仓库索引目录中删掉，不希望管理这个文件
2. `git restore --staged xx`：==将xx从暂存区里移除==
3. `git checkout — XX`或`git restore XX`：==将XX文件尚未加入暂存区的修改全部撤销==
## 代码回滚
1. `git reset --hard HEAD^`或`git reset --hard HEAD~`：将代码库回滚到上一个版本
2. `git reset --hard HEAD^^`：往上回滚两次，以此类推
3. `git reset --hard HEAD~100`：往上回滚100个版本
4. `git reset --hard 版本号`：回滚到某一特定版本
## 远程仓库
1. `git remote add origin git@git.acwing.com:xxx/XXX.git`：将本地仓库关联到远程仓库
2. `git push -u (第一次需要-u以后不需要)`：将当前分支推送到远程仓库
3. `git push origin branch_name`：将本地的某个分支推送到远程仓库
4. `git clone git@git.acwing.com:xxx/XXX.git`：将远程仓库XXX下载到当前目录下
5. `git push --set-upstream origin branch_name`：设置本地的`branch_name`分支对应远程仓库的`branch_name`分支
6. `git push -d origin branch_name`：删除远程仓库的`branch_name`分支
7. `git checkout -t origin/branch_name`：将远程的`branch_name`分支拉取到本地
8. `git pull`：将远程仓库的当前分支与本地仓库的当前分支合并
9. `git pull origin branch_name`：将远程仓库的`branch_name`分支与本地仓库的当前分支合并
10. `git branch --set-upstream-to=origin/branch_name1 branch_name2`：将远程的`branch_name1`分支与本地的`branch_name2`分支对应
## 分支命令
1. `git branch branch_name`：创建新分支
2. `git branch`：查看所有分支和当前所处分支
3. `git checkout -b branch_name`：创建并切换到`branch_name`这个分支
4. `git checkout branch_name`：切换到`branch_name`这个分支
5. `git merge branch_name`：将分支`branch_name`合并到当前分支上
6. `git branch -d branch_name`：删除本地仓库的`branch_name`分支
7. `git push --set-upstream origin branch_name`：设置本地的`branch_name`分支对应远程仓库的`branch_name`分支
8. `git push -d origin branch_name`：删除远程仓库的`branch_name`分支
9. `git checkout -t origin/branch_name`：将远程的`branch_name`分支拉取到本地
10. `git pull`：将远程仓库的当前分支与本地仓库的当前分支合并
11. `git pull origin branch_name`：将远程仓库的`branch_name`分支与本地仓库的当前分支合并
12. `git branch --set-upstream-to=origin/branch_name1 branch_name2`：将远程的`branch_name1`分支与本地的`branch_name2`分支对应
## stash暂存
1. `git stash`：将工作区和暂存区中尚未提交的修改存入栈中
2. `git stash apply`：将栈顶存储的修改恢复到当前分支，但不删除栈顶元素
3. `git stash drop`：删除栈顶存储的修改
4. `git stash pop`：将栈顶存储的修改恢复到当前分支，同时删除栈顶元素
5. `git stash list`：查看栈中所有元素