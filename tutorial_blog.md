# H1 Using Git to Implement a New Feature/Change


In this this tutorial we are going to walk through the steps on how to implement a new feature without affecting the main branch using Git. Git is a version control system used manage code for projects such as software development and infrastructure deployments. This tutorial will use a current project to guide you through the process of implementing a new feature. You can fork this project or follow along using your own project.

## Clone Repository
-------------------
We want to create a local copy of the project’s repository on our computer. Having a local copy of the repository allows us to work offline or continuing working if disconnected from the main repository. Copy the project’s repository clone HTTPS link. In your terminal, navigate to your project folder run the following command:
> ###### \# create clone of existing repository
```
$ git clone https://github.com/BigSave24/Weather-App-JavaScript.git
Cloning into 'Weather-App-JavaScript'...
remote: Enumerating objects: 43, done.
remote: Total 43 (delta 0), reused 0 (delta 0), pack-reused 43
Unpacking objects: 100% (43/43), done.
```

## Create A New Feature Branch
------------------------------
Now, we want to create a new branch to add the new feature to the project. Creating a new branch allows main project files to remain in a working state while new features are created and tested. You’ll notice multiple use of the git branch command. Although, it is not necessary, it is good practice to use this command to verify creation and/or switching between branches. To create a new branch run the following commands:
> ###### \# list branches
```
$ git branch
* master
```

> ###### \# create new branch
```
$ git branch new_feature_one
```

> ###### \# list branches
```
$ git branch
* master
  new_feature_one
```

> ###### \# switch to another branch
```
$ git checkout new_feature_one
Switched to branch 'new_feature_one'
```

> ###### \# list branches
```
$ git branch
  master
* new_feature_one
```

## Create New Features
----------------------
At this point, you ready to start developing the new feature for the project. Adding new features could include updating code in an existing file or adding a new file(s) to the project. For this tutorial, I will be adding an about.html page as the new feature update. The about.html file created prior to running the commands. To add updates to the project, use the following commands:
> ###### \# check status of git project files
```
$ git status
On branch new_feature_one
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	about.html

nothing added to commit but untracked files present (use "git add" to track)
```

> ###### \# add new and/or modified files to git staging area
```
$ git add about.html
```

> ###### \# check status of git project files
```
$ git status
On branch new_feature_one
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   about.html
```

> ###### \# save new and/or modified files to git local project repository
```
$ git commit -m "ADD about page feature"
[new_feature_one f579c13] ADD about page feature
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 about.html
```

> ###### \# check status of git project files
```
$ git status
On branch new_feature_one
nothing to commit, working tree clean
```

## Switch To Main Branch
------------------------
We are ready to integrate our new feature into the project’s main branch. Before merging our changes, we must switch back to the main branch, check, and sync any changes from its remote repository. Multiple people may be working on this project. Therefore, syncing any changes prior to merging and pushing our feature update will help avoid merge conflicts. Use the following commands to switch to main branch:
> ###### \# list branches
```
$ git branch
  master
* new_feature_one
```

> ###### \# switch to another branch
```
$ git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

> ###### \# list branches
```
$ git branch
* master
  new_feature_one
```

## Pull Down Main Branch Changes
--------------------------------
As stated before, we are going to sync any changes from the main branch remote repository to our local repository using the git pull command. This command will allow us to pull and merge any changes at the same time. Use the following commands to pull changes from the remote main branch:
> ###### \# check status of git project files
```
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

> ###### \# get and merge data from remote repository
```
$ git pull
Already up to date.
```

## Merge Changes From New Branch
--------------------------------
Now, we are ready to merge our new feature into the main branch. The main branch should be up to date with remote main branch. If any error(s) has occurred after running git pull the error(s) should be corrected before moving forward. Proceed with merging the new feature by using the following commands:
> ###### \# check status of git project files
```
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

> ###### \# merge changes to a branch
```
$ git merge new_feature_one
Updating 7e8bed5..f579c13
Fast-forward
 about.html | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 about.html
```

> ###### \# check status of git project files
```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

## Push Changes To Remote Repository
------------------------------------
Our project’s main branch now has the new feature integrated locally. These changes need to be updated on the remote repository’s main branch. Run the following commands:
> ###### \# check status of git project files
```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

> ###### \# push local branch changes to remote repository
```
$ git push origin master
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 271 bytes | 271.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/BigSave24/Weather-App-JavaScript.git
   7e8bed5..f579c13  master -> master
```

## Delete New Feature Branch
----------------------------
We have completed our new feature update to the project. The new feature branch is no longer needed. At this point, the branch can be deleted since all updates and merges were completed successfully. Use the following commands to delete a local branch:
> ###### \# check status of git project files
```
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

> ###### \# list branches
```
$ git branch
* master
  new_feature_one
```

> ###### \# delete a local branch
```
$ git branch -d new_feature_one
Deleted branch new_feature_one (was f579c13).
```

> ###### \# list branches
```
$ git branch
* master
```

> ###### \# check status of git project files
```
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```
