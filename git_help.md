#**CONFIGUE**
>查看系统config
>git config --system --list　　

>查看当前用户（global）配置
>git config --global  --list
 

>查看当前仓库配置信息
>git config --local  --list

>git config --global user.name 'Your Name'
>git config --global user.email 'Your Email@xxx.com'
---
#**CREATE REPOSITORY**
>git init
>git add xxx.txt
>git commit -m "interpretation....'
---
#**BACK**
>git status
>git diff
>git log
>git log --pretty=oneline
>git reset --hard HEAD^
>git reset --hard HEAD^^
>git reset --hard HEAD~100
>git reset --hard 1234522
>git reflog
---
#**WORK & STAGE**
>git status
>git add xxx.txt
>git commit -m "interpretation..."
>git diff HEAD --xxx.txt
>git checkout --xxx.txt
>git restore --xxx.txt
>git restore --staged xxx.txt
>git reset HEAD xxx.txt    (unstage)
>rm xxx.txt
>git checkout -- xxx.txt
>git rm xxx.txt
>git commit -m "remove xxx.txt"
>git reset --hard HEAD^
>git reset --hard 121312 (id number)
---
#**REMOTE**
>ssh-keygen -t rsa -C "youremail@example.com"
>git remote add origin git@github.com:examplename/example.git
>git remote rm origin
>git push -u origin master
>git push origin master
>git clone git@github.com:examplename/example.git
>git clone https://github.com/examplename/example.git
---
#**BRANCH**
```
Generally every developer has their own branch for their own work, then merge it to 'dev' branch for the new feature. And when the new version will be released, merge the 'dev' branch to the 'master' branch.
[master] <-- [dev] <-- [personal]
```
>git checkout -b dev
>git checkout dev
>git branch
>git branch dev 
>git branch -a
>git checkout master
>git merge dev
>git branch -d dev  (delete dev branch)
>git switch -c dev
>git switch dev
>
>git checkout -b feature
>git add xxx.txt
>git commit -m "feature interpretation..."
>git checkout master
>git add xxx.txt
>git commit -m "master interpreatation..."
>git merge feature (merge conflic)
>git merge --no-ff -m "merge with no-ff" feature
>mdify the file
>git add xxx.txt
>git commit -m "solve the conflict"
>git log --graph --pretty=oneline --abbrev-commit
>
>git branch -d feature
>git branch -D feature
---
#**BUG**
>git checkout -b dev
>git add xxx.txt
>git commit -m "modify..."
>git stash
>git checkout master
>git checkout -b issbug
>git add xbug.txt
>git commit -m "fix issbug"
>git checkout dev
>
>git stash list
>git pop
>
>git stash apply stash@{0}  
>git stash drop
>
>git cherry-pick
---
#**FEATURE**
>git checkout dev
>git checkout -b feature-vulcan
>git add vulcan.py
>git commit -m "add feature vulcan"
>git checkout dev
>git merge --no-ff -m "merge feature vulcan" feature-vulcan
>git branch -d feature-vulcan
>git branch -D feature-vulcan
---
#**COOPERATION**
>git remote
>git remote -v
>git remote show origin
>git push origin dev
>git push origin master
>git checkout -b dev origin/dev
>
>git push origin dev  (confliction happens)
>git pull
>git branch --set-upstream dev origin/dev
>git add fixconflict.txt (solve the conflict)
>git commit -m "merger & fix conflict"
>git push origin dev

>git branch -a
>git push origin --delete <remote subbranch name>
---
#**TAG**
>git tag
>git show tag_name
>git tag -a v1.0 -m "version 1.0 released"  1234(pointer id)
>git tag -d v1.0
>
>git push origin v1.0
>git push origin --tags
>
>delete tag:
>git tag -d v0.9
>git push origin :refs/tags/v0.9

#.gitignore
```
# Windows:
Thumbs.db
ehthumbs.db
Desktop.ini

# Python:
*.py[cod]
*.so
*.egg
*.egg-info
dist #文件夹
build #文件夹
```
>git add .gitignore
>git commit -m "add xxx file" 
>git add -f *.egg
>git check-ignore -v *.egg

#alias
```
$ git config --global alias.co checkout
$ git config --global alias.ci commit
$ git config --global alias.br branch

git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

```
$ cat .git/config 
[core]
    repositoryformatversion = 0
    filemode = true
    bare = false
    logallrefupdates = true
    ignorecase = true
    precomposeunicode = true
[remote "origin"]
    url = git@github.com:michaelliao/learngit.git
    fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
    remote = origin
    merge = refs/heads/master
[alias]
    last = log -1
```

```
$ cat .gitconfig
[alias]
    co = checkout
    ci = commit
    br = branch
    st = status
[user]
    name = Your Name
    email = your@email.com
```

