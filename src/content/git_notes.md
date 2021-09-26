---
title: "Git commands in 5min"
date: "2021-09-07"
draft: false
path: "/blog/git-notes"
---
# Git Notes

## **Repositories:**
1. There are remote repos and local repos.
    - Remote are the onces hosted on server and everyone has access.
    - Local is the one present on the system.

## **Setup a local git repo**
1. To create a local repo. create a folder move into it.
2. execute the command ***git init***

## **Staging in git**
1. When ever you create a git repo. You can include individual files which you want to maintain version.
2. Now you need to execute ***git add file_name*** this will include the file in staging area.
3. You can only commit the files that are added.
4. Alternatively you can execute ***git add . / git add -A*** (*Which will include all the files*)

## **Commit in git**
1. A commit is a snsapshot of the project and all the files included.
2. for every commit we generate a unique hashcode to identify it.
3. To commit you can execute
    - ***git commit***
    - ***git commit -m 'commetns'***
4. ***git push -u origin master(optionl)*** this command will pusblish the master(local) to the remote repo and **-u** will be used to track the branch.
5. once you use -u from next you can use ***git push/pull***

## **Git logs:**
1. To view the logs or previous commits you can use command
    - ***git log*** - full length log.
    - ***git log --graph*** - graphical commits.
    - ***git log --oneline*** - oneline history.

## **Add a remote the local repo**
1. If the repo is creatd in the local we have to setup a upstream.
2. use this command ***git remote add origin(remote name) < url link >***
3. use ***git remote -v*** to view the remotes.

## **Branches:**
1. We have two types 
    - Local branch
    - Remote Branch
2. ***git branch < new branch name >*** - To create branch
3. ***git branch < new branch name > xHexCode(commit id)***
4. ****git checkout/switch < branch name >***
5. ***git branch -m < new branch name >*** *changes the current branch name*
6. ***git branch -m < old nbeanch name > < new branch name >***(Non head branch)
7. git push -u origin/< local branch name> - this is to publish a local branch to the remote for first time.
8. ***git branch --track < local name> origin/< remote branch name>*** ( To get a branch from remote)
9. ***git checkout --track origin/< remote br name>***
10. If we have tracking is set correctly we can pull push easily
    - git pull
    - git push
    - git branch -v
    - ### *Ahead*:
        - having uncommited branches in local
    - ### *Behind*:
        - having commits in remote not pulled.
11. To delete a branch checkout other branch and delete the branch.
    - ***git -d branch_name***
12. TO delete a remote the branch on the remote
    - **git push origin --delete branch_name**
    - *Remember to delete all the counter part branches.*
13. We always integrate the changes from other branches **INTO YOUR LOCAL BRANCH**
14. Mergin branches:
    - Switch into the branch in which you want to merge the changes into.
    - execute **git merge < other_branch_name >**
    - The merge creates a merge commit give the message.
15. Rebasing the brahces.
    - checkout to the base brach.
    - execute **git rebase < branch name>**
16. Comparing the difference in branches.
    - execute ***git log branch1...branch2***
        - this will give the commits in b2 but not in b1
    - execute ***git log origin/main...main***
        - this will give the commits diff in remote to the local

## **Branching Strategies:**
1. Strategy 1: We need to maintain long running Branches.
    - One master, one Dev, and feature branches must be taken from dev and integrated into dev bracnch.
2. Strategy 2: One version, One branch.
    - In this we maintain different versions of one software and integrate featues into different versions.
    - Each version will have a master dev etc branch and all the branches will have one common branch.
3. One bug for each branch.

## **Mergin, Rebase and Conflicts:**
1. Merging branches:
   -  Switch into the branch in which you want to merge the changes into.
    - execute ***git merge < other_branch_name >***
The merge creates a merge commit give the message.
2. Rebase: Rebase makes the history look like it went in one timeline. No banches happened.
    - checkout to the base brach.
    - execute ***git rebase < branch name>***
3. Conflict is when there is some different version at the same place conflict occurs we have to take the required files and add,commit.
4. If you want to automaticall take from branches.
    - ***git merge -X <ours|theirs> <branch-name>***
    - ex: git merge -X ours login-feature.

## **Tags in Git:**
1. Tags are used to maintain inportant details about the branch.
2. add using ***git tag -a <tag-name>***  //  ***git tag -a v0.1 -m ’v0.1 stable release, changes from...’***
3. Deleting the tags ***git tag -d < tag-name>***

## **Deleting Commits**
1. ***git reset --hard HEAD~*** - last commit is deleted.
2. ***git reset --hard HEAD~ n*** - deletes n ancestors.

## **All about Commits**
1. To visit a previous commit
    - use ***git checkout < 7d checksum>***
    - use ***git checkout branch_name*** to get normal
2. To Undo a commit
    - use ***git revert <7d checksum you want to remove>*** this will ignore the changes in the commit specified and create a new commit idntical to the previous 2nd commit.

    A -> B -> C // git revert C // A -> B -> C -> D(same as B)
3. To remove the unstaged changes(This will permanently remove the changes)
    - use ***git clean -f*** , meaning our
project matches the most recent commit.

## Stay updates with the Remote and fork
1. use fetch command to get the commits into youe repo.
    - ***git fetch origin master***
    - Then merge it into the local master
    - THen push into your remote.