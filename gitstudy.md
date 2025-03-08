# Git学习笔记

## 如何向别人的项目提交自己的代码
1. 首先，fork别人的项目到自己的仓库中，记住这一步是在github上通过点击fork按钮完成的。
2. 然后，将自己的仓库clone到本地，记住这一步是在本地通过git clone命令完成的。命令如下：
``` bash
git clone https://github.com/yourname/yourproject.git
```
3. 然后在本地新建一个分支进行开发，为不影响主分支，命令如下：
``` bash
git checkout -b yourbranch
```
4. 然后在本地进行开发，开发完成后，将本地的代码推送到自己的仓库中，命令如下：
``` bash
git add .
git commit -m 'your commit message'
```
此时本地分支的修改已经提交到你自己的github上了，现在我们需要把这些修改pull request到原作者的仓库里，首先为了保证原作者的仓库是最新的，需要先pull一下，命令如下：
``` bash
git remote add upstream https://github.com/original-owner/resp-name.git
git fetch upstream
git merge upstream/main //把原作者的仓库合并到本地
```
OK，此时我们需要把所有提交修改到远程自己的github上，命令如下：
``` bash
git push -u origin yourbranch
```
现在我们就可以在github上发起pull request了，成功发送之后，原作者那边会收到pull requests请求消息！等待原作者的审核，如果审核通过，那么恭喜你，你的代码已经成功合并到原作者的仓库中了！

### github项目原作者如何处理其他人的pull requests
1. 首先，原作者需要在github上点击pull requests按钮，然后点击对应的pull requests请求，点击merge pull request按钮，然后点击confirm merge按钮，此时原作者的仓库中就会有其他人的代码了！
2. 但是，原作者的仓库中可能还有其他人的pull requests请求，所以原作者需要继续点击pull requests按钮，然后点击对应的pull requests请求，点击merge pull request按钮，然后点击confirm merge按钮，此时原作者的仓库中就会有其他人的代码了！ 依次类推，直到所有pull requests请求都处理完毕！

### 本地仓库如何提交github仓库

1. 首先，有一条信息需要注意，目前不支持用户名字和密码的验证方式提交github了，所以要采用其它方式，这里我推荐用personal access token的方式提交github，具体操作如下：
2. 首先，在github上点击settings按钮，然后点击personal access tokens按钮，然后点击generate new token按钮，然后在token description中填写一个描述，然后在expiration中选择一个过期时间，然后在scopes中选择repo，然后点击generate token按钮，此时会生成一个token，这个token就是我们需要的了，然后将这个token复制到本地的git config中，命令如下：
3. 本地git config中添加token，命令如下：
``` bash
   git remote add origin https://yourname:yourtoken@github.com/yourname/yourproject.git # 其实就是原来的https地址加上用户名和token
```
4. 然后，将本地仓库的代码推送到github仓库中，命令如下：
``` bash
git push -u origin main
```
5. 然后，就可以在github上看到自己的代码了！