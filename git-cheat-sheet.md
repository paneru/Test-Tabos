

GIT QUICK REFERENCE GUIDE #GITCheatSheet
===========================================

Creating new branch
-------------------

Create new branch called exp-1

```bash
git branch exp-1
```

Renaming existing branch
------------------------

Rename new branch exp-1 to feature-4 (Only perform this after adding and commiting all updates on exp-1 otherwise the result may be unexpected)

```bash
git branch -m exp-1 feature-4
```


Listing the branches
--------------------

```bash
git branch
```

We have four branches here:

```console
*branch-1
 master
 exp-1
 exp-2
```

Switching to different branch (e.g to exp-2 branch)

```bash
git checkout exp-2
```

Return back to MASTER:

```bash
git checkout master
```

Pushing the local branch to GitHub
----------------------------------

If you have to push the exp-2 branch to the Github

```bash
git push -u origin exp-2
```

Deleting local/experimental branch
----------------------------------

If you have to delete the exp-2 branch

```bash
git branch -d exp-2
```

Deleting remote branch on GitHub
--------------------------------

If you have to delete the exp-2 branch on the Github repo

```bash
git push origin :exp-2
```

OR

```bash
git push origin --delete exp-2
```


Push the MASTER branch to the Github
------------------------------------

```bash
git push -u origin master
```

Adding new file
---------------

This adds the new file to your current branch.

```bash
git add new-file.txt
```

Commiting new file
------------------

```bash
git commit -m "Message to add here" new-file.txt
```

Merge the changes
-----------------

If you wish to merge commited changes of story#3 into your master

```bash
git checkout master
git merge issue#3
```

Viewing the log messages
------------------------

If you wish to view clean log 5 lined commited messages

```bash
git log -5 --pretty=oneline
```

If you wish to view clean log 5 lined commited messages with extra information like author and time when it was commited

```bash
git log -5 --pretty=format:"%h - %an, %ar : %s"
```
