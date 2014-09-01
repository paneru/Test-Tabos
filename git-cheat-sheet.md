

GIT QUICK REFERENCE GUIDE #GITCheatSheet
===========================================

Clone new branch as 'disney'
----------------------------

```bash
git clone git://github.com/zendframework/ZendSkeletonApplication.git disney --recursive
```

Creating new branch
-------------------

Create new branch called exp-1

```bash
git branch exp-1
```

Downloading/pulling existing remote branch to local repo
--------------------------------------------------------

Pull/Download remote branch called BB-35 as BB-35-PP. Command below also checks out into the new branch i.e BB-35-PP

```bash
git checkout -b BB-35 origin/BB-35-PP
```
If you have error:

```bash
fatal: git checkout: updating paths is incompatible with switching branches/forcing
Did you intend to checkout ‘origin/‘ which can not be resolved as commit?’
```

Then try the pull first and try above command

```bash
git pull
```

Undo the merge
--------------

If you wanted to undo the merge, please do the following:

```bash
git pull $REMOTE $BRANCH
# uh that went wrong??? WTF %*4£
git reset --hard ORIG_HEAD
# thats's coooool
```

Find defference between your local branch and remote branch

```bash
git diff master origin/master
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

Migrating existing project from GitHub to BitBucket
====================================================

View actual URL aliases for you local repo
------------------------------------------

```bash
git remote
git remote -v
```

Detach your local repo from GitHub
----------------------------------

```bash
git remote rm origin
```

Create a GIT project (myproject) in BitBucket (Simply logon to BitBucket and follow instructions)

Add/Initilise your project to BitBucket
---------------------------------------

```bash
cd /path/to/your/local/repo
git remote add origin https://username@bitbucket.org/username/myproject.git
```

Finally push your project to BitBucket
---------------------------------------

```bash
git push -u origin master
```

Viola!! (Its done and your first commit is listed on BitBucket)

Re-link to new repo if the project has been created on Bitbucket
--------------------------------------------------------------

This is useful if your team member has updated the repo on Bitbucket

(Using https):
--------------
```bash
git remote set-url origin https://<username>@bitbucket.org/<projectName>/<projectName>.git
```

(Using SSH):
------------
We have to generate private and public key to start with.
If we already have one, we can simply use the public key and add it to the Bitbucket. Bitbucket can also use deployment keys which is read only. Deployment keys are useful for server instances.

Check to see if the public ket exists:

```bash
cat ~/.ssh/id_rsa.pub
```

if you see the key then you can copy the key by running follwing on terminal.

```bash
xclip -sel clip < ~/.ssh/id_rsa.pub
```
(** xclip is an application that needs to be installed before using it. Run on CLI to install: sudo apt-get install xclip)

Once the public key is copied in your clipboard, head over to bitbucket and add SSH keys under Account Management. Give it a name that best describes the location of your computer.


Now verify the configuration by running the command on terminal.

```bash
ssh -T git@bitbucket.org
```
If output shows your bitbucket username, then you are ready to edit your GIT config file on your computer.

```bash
sudo gedit .git/config
```

You will need to replace HTTPS link with:

```bash
git remote set-url origin git@bitbucket.org:paneru/zf2AuthSha.git
git remote set-url origin git@bitbucket.org:weareifp/walt.git
```

url = git@bitbucket.org:AccountName/RepoName.git

or SSH: url = ssh://git@bitbucket.org/AccountName/RepoName.git

OR,

url = git@bitbucket.org:weareifp/bluebird.git

or SSH: url = ssh://git@bitbucket.org/weareifp/bluebird.git

Save and close the file. Its all done for you.

WORKING WITH .gitignore
=======================

To add files/directory that we want to be ignored, please use following:
(say we want to ignore 'application.db.php' file)

```bash
echo "application.db.php" >> .gitignore
```

We can simply open the file on your favourite editor as well. Above command is quick to implement.


