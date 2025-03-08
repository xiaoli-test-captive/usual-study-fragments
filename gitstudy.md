# Git学习笔记

## 如何向别人的项目提交自己的代码
1. 首先，fork别人的项目到自己的仓库中，记住这一步是在github上通过点击fork按钮完成的。
2. 然后，将自己的仓库clone到本地，记住这一步是在本地通过git clone命令完成的。命令如下：
3. git clone https://github.com/你的用户名/项目名.
4. 进入克隆下来的项目文件夹：

下面是一系列常用的Git命令：
```bash
git init  # 初始化一个新的Git仓库
git add .  # 将所有文件添加到暂存区
git commit -m "Initial commit"  # 提交暂存区的文件到本地仓库
git push origin master  # 将本地仓库的文件推送到远程仓库的master分支
   