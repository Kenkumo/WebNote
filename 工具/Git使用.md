# Git
## 初始化git仓库
`git init`
## 设置当前使用用户
`git config --global user.name "xiaosu"`
`git congig --global user.email "sujianyun2019@163.com"`
## 将文件放入仓库
`git add ./filename`	`git add ./`
`git commit -m "描述"`	`git commit --all -m "描述"`
## 查看状态
`git status`
## 查看日志
`git log`
`git log --oneline` 查看精简版日志
## git版本回退
`git reset --hard Head~0`回到上一次代码提交时的状态
`git reset --hard Head~1`回到上上一次代码提交时的状态
`git reset --hard 版本号`通过版本号切换版本
`git reflog`历史版本切换记录
## git创建分支，切换分支
`git branch dev`创建dev分支
`git branch -d dev`删除dev分支
`git branch`查看分支
`git chekout dev`切换分支
`git merge dev`将dev分支合并到master分支
## 提交代码到github(当做git的服务器)
`git push https://github.com/Kenkumo/LearnNote.git master`把当前分支的内容上传到远程的master分支上
`git pull 地址 master`下载代码--前提是本地要初始化一个仓库`git inint`
`git clone 地址`下载代码，多次执行会覆盖本地内容
## 通过SSH方式上传代码
公钥(给github) 私钥(自留)，两者间有关联
生成公钥和私钥：`ssh-keygen -t rsa -C "sujianyun2019@163.com"`
## 在push和pull操作时
先pull在push
## 添加远程地址
`git remote add origin 地址`
`git push origin master`
`git push origin -u master` 用-u参数（将当前分支与远程的指定分支进行关联），下次直接使用git push



