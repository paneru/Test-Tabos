

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


If you have to push the master branch to the Github

```bash
git push -u origin master
```
