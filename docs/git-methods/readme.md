<!-- Date: 2016-07-09 02:20 -->

# git 常用命令

最常用的 `git` 命令

| 命令                                           | 作用                                                                                                       |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `git init`                                     | 初始化本地仓库                                                                                             |
| `git status`                                   | 查看版本库状态                                                                                             |
| `git add <文件名>`                             | 保存修改到暂存区                                                                                           |
| `git commit`                                   | 保存暂存区到版本库                                                                                         |
| `git log`                                      | 查看所有的 commit 日志                                                                                     |
| `git reglog`                                   | 查看所有的操作日志                                                                                         |
| `git diff`                                     | 查看工作区与暂存区的区别，可以指定文件                                                                     |
| `git diff HEAD`                                | 查看工作区与最新版本库的区别，可以指定文件                                                                 |
| `git diff --cached`                            | 查看暂存区与最新版本库的区别，可以指定文件                                                                 |
| `git reset --mixed(默认) <版本名>`             | 回退到指定版本，保留工作区，清空暂存区，暂存区和版本差异全部放进工作区                                     |
| `git reset --hard <版本名>`                    | 回退到指定版本，暂存区和工作区完全重置                                                                     |
| `git reset --soft <版本名>`                    | 回退到指定版本，保留工作区，重置 HEAD`带来的差异放进暂存区                                                 |
| `git branch`                                   | 查看所有分支 星号后面的表示当前工作区所在的分支                                                            |
| `git branch <分支名>`                          | 创建新的分支                                                                                               |
| `git branch -d <分支名>`                       | 删除指定分支                                                                                               |
| `git branch -D <分支名>`                       | 强行删除指定分支(如果新分支内容未被主分支合并,会有提示)                                                    |
| `git switch <分支名>`                          | 切换到指定分支                                                                                             |
| `git switch -c <分支名>`                       | 从当前分支创建新分支并自动切换到新分支                                                                     |
| `git switch -c <分支名> <起点>`                | 从指定分支创建新分支并自动切换到新分支                                                                     |
| `git switch -C <分支名>`                       | 从当前分支创建新分支并自动切换到新分支，如果分支名不存在，创建新分支，否则会重置分支内容和当前分支一模一样 |
| `git switch -C <分支名> <起点>`                | 从指定分支创建新分支并自动切换到新分支，如果分支名不存在，创建新分支，否则会重置分支内容和指定分支一模一样 |
| `git restore <文件名>`                         | 撤销工作区中某文件的修改                                                                                   |
| `git restore --storage <文件名>`               | 撤销暂存区某文件的修改                                                                                     |
| `git merge <分支名>`                           | 合并分支内容，使用 fast-forward`模式                                                                       |
| `git merge <分支名> --no-ff`                   | 合并分支内容，不使用 fast-forwad` 模式，可以看到合并前的 commit` 记录                                      |
| `git stash`                                    | 临时保存当前分支的数据                                                                                     |
| `git stash list`                               | 查看当前分支之前的存档点                                                                                   |
| `git stash apply <存档点名称>`                 | 把分支数据恢复到指定的存档点                                                                               |
| `git stash drop <存档点名称>`                  | 删除指定的存档点                                                                                           |
| `git stash clear`                              | 删除所有的存档点                                                                                           |
| `git stash pop`                                | 把分支数据恢复到之前临时存档点，并删除存档点记录                                                           |
| `git remote -v`                                | 查看当前仓库对应的远程仓库信息                                                                             |
| `git push <仓库名> <分支名>`                   | 把当前分支内容推送到远程仓库的指定分支                                                                     |
| `git pull`                                     | 从远程仓库拉取最新版本                                                                                     |
| `git clone <仓库名> <保存路径>`                | 从远程仓库克隆项目到本地，可以另外指定项目文件名                                                           |
| `git checkout <分支名>`                        | 切换到指定分支                                                                                             |
| `git checkout -- <文件名 s>`                   | 撤销工作区中某文件的修改                                                                                   |
| `git switch -c <分支名> <远程仓库名/分支名>`   | 在本地创建新分支，并将其关联到远程仓库的指定分支                                                           |
| `git checkout -b <分支名> <远程仓库名/分支名>` | 在本地创建新分支，并将其关联到远程仓库的指定分支                                                           |
| `git rebase <分支名>`                          | 变基合并                                                                                                   |
