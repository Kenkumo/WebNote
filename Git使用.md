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
 
