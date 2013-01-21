

GIT QUICK REFERENCE GUIDE #GITCheatSheet
===========================================

Creating new branch
-------------------

Create new branch called exp-1

```bash
git branch exp-1
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



