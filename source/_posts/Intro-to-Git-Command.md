---
title: Introduction to Git Command
date: 2019-02-10
tags:
- Git
---

## [Creating repository](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013743256916071d599b3aed534aaab22a0db6c4e07fd0000)

- `git init`: creat a repository
- `git add File_Name`: add "File_Name" to repository
- `git add .` : add all files 
- `git commit -m "message"`: commit changes and tell others what changes have been made 

<!--more-->

---

## [Way-back Machine](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013743858312764dca7ad6d0754f76aa562e3789478044000)



- `git status`: tell you which files have been changed 
- `git diff`: check what content exactly has been changed in each file

### [Time Travelling](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013744142037508cf42e51debf49668810645e02887691000)

- commitID: git uses commit ID, a hex number calculated by SHA1 to record your commit history

- HEAD: HEAD is the current version, HEAD^ is the previous, HEAD^^ is the one before the previous, HEAD~100 is the last 100.

- `git log`: check the commit history

- `git reflog`: check the command history

- `git reset --hard CommitID` : Going back to the "Commit ID" version

  (e.g. `git reset --hard HEAD^` : going back to the previous version)

- When you go back, the "future version" will no longer appear in "`git log`". However, you can use "`git reflog`" to trace "commit ID" from the future

![Working Directory and Repository](https://cdn.liaoxuefeng.com/cdn/files/attachments/001384907702917346729e9afbf4127b6dfbae9207af016000/0)

### [Undo Changes](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374831943254ee90db11b13d4ba9a73b9047f4fb968d000)

1. messed up with working directory: use `git checkout -- File_Name` to discard changes in working directory and make "File_Name" to go back to the latest "committed" or "added" version

2. messed up with working directory and added it to stage: use `git reset HEAD File_Name` to discard changes in stage but keep "File_Name" in working directory changed, therefore going back to situation 1

3. committed the mess to master branch: use the *Time Traveling* technique in the previous section

### [Deleting Files](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013758392816224cafd33c44b4451887cc941e6716805c000)

If you want to delete files that are already committed to the master branch:

1. delete the file in working directory: `rm File_Name`
2. delete the file from git / restore the file
   1. delete the file from git: `git rm File_Name` & `git commit`
   2. restore the file: `git checkout -- File_Name`

---

## Managing Branch

### [Creating and Deleting Branch](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001375840038939c291467cc7c747b1810aab2fb8863508000)

- 查看分支：`git branch`
- 创建分支：`git branch <name>`
- 切换分支：`git checkout <name>`
- 合并某分支到当前分支：`git merge <name>`
- 删除分支：`git branch -d <name>`

### [Solving Conflicts](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001375840202368c74be33fbd884e71b570f2cc3c0d1dcf000)

