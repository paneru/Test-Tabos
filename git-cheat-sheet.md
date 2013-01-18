

GIT QUICK REFERENCE GUIDE #GITCheatSheet
===========================================

Listing the branches
--------------------

```bash
git branch
```

*branch-1
 master
 exp-1
 exp-2

we have four branches here.

Switching to different branch (e.g to exp-2 branch)

```bash
git checkout exp-2
```

We can return to master by doing:

```bash
git checkout master
```


Pushing the local branch to GitHub
----------------------------------

If you have to push the exp-2 branch to the Github

```bash
git push -u origin exp-2
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


If you have to push the master branch to the Github

```bash
git push -u origin master
```

Adding new file
---------------

```bash
git add new-file.txt
```

Commiting new file
------------------

```bash
git commit -m "Message to add here" new-file.txt
```



