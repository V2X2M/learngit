Git is a version control system  
Git is free software  

## Step For First Programma
- git config --global user.name "V2X2M"  
- git config --global user.email "lxkqv@outlook.com"  
- mkdir -p ~/Github/learnGit/  
- cd ~/Github  
- git init # initialize git directory "~/Github", A hidden directory "Github/.git/" was created  
- cd learnGit/  
- vim readme.txt  
- git add readme.txt # The number of file are no limited  
- git commit -m "There is a description" # commit all files  

## git 穿越
- git log # View content which is change
- git reset --hard HEAD^ #回退到上一个版本,HEAD^^^或HEAD~100
- git reset --hard a4ef3f #再到最新的版本，或者指定版本号从而回到指定版本。版本号·写5位数字以上
- git reflog #在任何时间查看任何 穿越 过的文件

**以上几步只是建立了本地git仓库，提交和回退版本也只是在本地git仓库**

## 建立远程仓库并与本地仓库关联
- ssh-keygen -t rsa -C "lxkqv@outlook.com" # 创建ssh密钥 ,一路回车
- nvim ~/.ssh/id_rsa.pub # 复制密钥到github.把每台电脑的ssh-key添加到github就能在每台电脑上连接github
- 在github网站上建立一个远程仓库，但嫑初始化，即嫑 README.md 文件
- git remote add origin https://github.com/V2X2M/learngit.git
- git push -u origin master #把本地仓库的所有内容推送到远程仓库，-u可看作union，即把本地和远程仓库关联



# git CW
git init # initialize git
git add . # add all file of current dir
vim修改文件
git diff # 查看文件有什么改动
再次添加git add .
git status # 查看当前文件的提交状态
git reset # 撤回添加的更改

commit之前确保已经表明自己的身份

- git config --global user.name "V2X2M"  
- git config --global user.email "lxkqv@outlook.com"  
- git config credential.helper store
git commit -m "描述"
git commit<CR> #打开默认编辑器输入您的描述
git config --globle core.editer #默认编辑器

vim .gitignore #添加忽略提交的文件
git rm --cached file # 从repository里删除之前追踪的文件

## git分支
git branch picture #创建分支
git checkout picture #切换到picture分支
git checkout master #切换到 主 分支
git merge picture #把刚刚建立的分支picture合并到 master
git branch -d picture #删除分支picture
git branch -D picture #如果picture没有合并到主分支，仍然强制删除

## git项目
- github网站上手动建立项目（存储库）
- copy项目地址:git clone http://
- 对git clone的分支文件更改后，可以有以下两种提交方式:
  - add && commit: 两个命令只会提交到**分支**上
  - git push # 提交到github**主分支**。push时要么指定文件名，要么就在对应的目录下。最好是后者。
  - git pull # pull最新的版本

