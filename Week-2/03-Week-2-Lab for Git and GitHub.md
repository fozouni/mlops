# Amazing world of Git

Git is a free and open source distributed **Version Control System (VCS)** designed to handle everything from small to very large projects with speed and efficiency.

[toc]

## Installing Git

https://git-scm.com/download/win

🛑 If you have already installed Git and a new version has been released recently, just run this command on your PowerShell or CMD:

```powershell
winget install --id Git.Git -e --source winget

# winget is a package manager in windows and is similar to Choco. But choco is more advanced and rpofessional. 
```

```bash
mkdir mlops

cd mlops 

git init
 
git status

git add .

# After running "git add .", the changes will be staged, and you can proceed to create a commit using the "git commit" command.

# "staging" refers to the process of preparing changes to be included in the next commit.

git commit -m "my first try"

ERROR

git log --pretty=format:"%an <%ae>" | sort -u
# see if there were any users on the computer

git config --global user.email "fozouni@hotmail.com"
git config --global user.name "fozouni"
```



## Go to Github

Make a repository with the same name as your local folder

```bash
git remote add origin https://github.com/fozouni/repository.git
```



## Create Keys for interacting with GitHub

```bash
cat .git/config

ssh-keygen.exe

#or 

ssh-keygen -t ed25519 -C "your_email@example.com"

# Now put the public key in your github setting part
```



## Go to .git/config

You should see something like this

```yaml
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "origin"]
	url = https://github.com/fozouni/repository.git
	fetch = +refs/heads/*:refs/remotes/origin/*
```



## Rename the current branch to `main`

```bash
git branch -M main

# will change the branch from master to main

git push -u origin main
# The command git push -u origin main is used to push your local Git repository's branch named "main" to the remote repository named "origin." The flag -u is for --set-upstream, is used to set up the tracking relationship between the local branch and the remote branch
```



## Change a file

```bash
notepad script.py
#or
nano script.py

git status

git add .\script.py

git push origin main

git log
# or git log --oneline

git show <COMMIT NUMBER>
```



## Commit from GitHub 

Make a change in a file in GitHub and then. The following command pull all the new changes that have been done in GitHub.

```bash
git pull 
```



## Create some branches from cli

```bash
git branch -a

git branch -c de1

git checkout de1
# will switch the branch

#or
git checkout -b de1

notepad .gitignore
#or
nano .gitignore

# inside file write for example file.txt which is the home of your passwords

git add .

git commit -m ".gitignore file has been added"

git push -u origin main
```



## Rolling back

**This depends on these conditions**

1- Our file has been staged or not?

2- Our file has been committed or not? 

```bash
🛑🛑🛑 Before any Commit

git checkout file.name
#will undo the changes before commiting

git diff
# before staging a file it will show us the difference
# git diff --cached

git restore --staged jupyter1.ipynb
# will undo files for us if they have gone to staged level

🛑🛑🛑 Commited a file?

git log --oneline

git diff ace00c4..7dfdf5c

git reset --hard ec62a6f
# every commit after "ec62a6f" will be removed 
```
