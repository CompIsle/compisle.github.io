![](https://git-scm.com/images/logos/downloads/Git-Logo-1788C.png)
## What it is, basics of use, what is covered
##### Ashley Oliver, March 2017, revised Sep 2021

Git is an scvs, a source code versioning system.

That is to say it can track a file or collection of files and record changes in a database. Later you can discover what the changes were or use them to revert to any earlier version. This is already useful  for 

+ source code
+ web sites
+ assignments

all can make use of this. 
It can be used simply as a (superior) kind of backup. It can do a lot more besides. 

Two quick examples of things git can do *not* covered in this guide: 

+ allow multiple versions of a set of files to exist and be being worked on at the same time while remaining independent of each other - this is covered by the **branch** commands
+ make  a **pull** request, that is 	 **push** any changes you might make with your **clone** of  a remote master version back to the server for a potential **merge** in to the online master - possibly with changes made by other people to different parts also being merged. Team-working and publishing, in other words.

This guide covers the very basics and how to use git to track changes you have made as a single user.

Another useful quick guide is [here](http://rogerdudler.github.io/git-guide/) - however it assumes that you are working with a remote repository which probably won't be initially.

## Getting started

Check that git is installed - from a command line prompt (either cmd.exe or powershell though the latter is to be preferred) simply type **git**.

```>git```

If you get usage prompts all is well. If you get 'no such command' ask someone how to install git.

Let's make some files and folders to play around with (or you could use something you already have and play with that). Git works with folders though, not really with loose files (all subfolders under a folder containing a repository are assumed to be part of that repository).
I am typing the following (PowerShell)

```bash
>cd c:/tmp
>mkdir root/b
>cd root
>echo >sample1.txt 'Hello World'
>echo >sample2.txt 'Hello again, World'
>echo >b/sample3.txt 'Still no answer, World?'
```
(*odd random highlighting in console 'dumps'  due to language issues*)

So, at this point we have two folders with three dummy text files in them. We should be in folder **c:/tmp/root** which is the 'root' of our file structure. Now we need to put this folder under git control (aka make a new repository). You *must* be in the right folder before you do this. (Powershell by default shows the current folder as part of the prompt, so this is easy to see)

```bash
>git init
Initialized empty Git repository in C:/tmp/root/.git/
```
Key thing here is 'empty' we have created an *empty* respository. It is in root/.git  (which you may or may not be able to see depending upon your settings for seeing hidden files; in powershell at least **Get-ChildItem -Force** or **gci -fo** will show hidden files).

(If you prefer to create the backup at the same time, see the end of this document)it to you).

To tell git which files we want to track we need to add them to the repository (filestore, database, where git keeps changes).
```bash
>git add .
```
This adds everything in the current folder and its sub-folders.[^fna] 

[^fna]:It is possible to have git ignore certain files by pattern or extension - for instance if working in Python there is no point in  tracking *.pyc files or you might have some very large static resources (images, movies, databases) that you do not want as part of your archive. Read about **.gitignore** if you need to do that.

There is no message which is fairly usual when things have gone ok. The usual rule is 'errors only'. If we want to see what we have done we could use the status command.type 

```bash
 >git status
On branch master
Initial commit
Changes to be committed:
  (use "git rm --cached <file>...
        new file:   b/sample3.txt
        new file:   sample1.txt
        new file:   sample2.txt
```
What this is telling us is that these three files (and a sub-folder) are now being watched BUT are only 'changes to be committed' - nothing has yet been made permanent. Git also helpfully tells us how to remove something from this list. We *do* want to record our initial state so the next step is to commit  ...
```bash
> git commit -m 'Initial commit'
[master (root-commit) 9f7b18f] Initial commit
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 b/sample3.txt
 create mode 100644 sample1.txt
 create mode 100644 sample2.txt
```
Just **git commit** would have been an alternative in which case you would be invited to add a message. A commit should always have a message. "Initial commit" is the usual messge for a fresh repository.
This tells us that three files were successfully added.[^fnb]

[^fnb]:More detail: the 9f7b18f is a (part of) the *hash* for this commit, a unique identifier, which could be used to 'roll-back' to this state at any future time. You may also provide [tags](https://git-scm.com/book/en/v2/Git-Basics-Tagging) if you want a friendly label. The 'master' is the name of this branch, it could be anything, but defaults to master - most people use this name for the main, stable branch.

## Basic Workflow Summary

+ Create a repository using **git init** (once)
+ Add files to track (once per file, multiple files can be added) **git add**
+ Commit files that have changed since the last commit **git commit**

This might be all you want to do, but usually we want a secure remote as well. See [Using a Remote](#using-a-remote).


## Some Party Tricks

Okay we have a repo.
Let's delete all our files - by mistake.

```bash
C:\Users\ashley> cd c:/tmp
C:\tmp> ls


    Directory: C:\tmp


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       20/03/2017     16:20                root


C:\tmp> cd root
C:\tmp\root [master]> git status
On branch master
nothing to commit, working tree clean
C:\tmp\root [master]> ls


    Directory: C:\tmp\root


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       20/03/2017     16:15                b
-a----       20/03/2017     16:13             28 sample1.txt
-a----       20/03/2017     16:15             42 sample2.txt


C:\tmp\root [master]> rm -fo b
...
C:\tmp\root [master +0 ~0 -1 !]> rm -fo *.txt
C:\tmp\root> ls
C:\tmp\root [master +0 ~0 -3 !]> ls
C:\tmp\root [master +0 ~0 -3 !]>

```

(confirmations of deletes omitted to save space)

So as the last **ls** shows we have now destroyed all our files! 
>Oh noes! My work iz gone!

Except ... we haven't.

```bash
>git checkout master -f
>ls
    Directory: C:\tmp\root


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----       21/03/2017     12:11                a
-a----       21/03/2017     12:11             30 sample1.txt
-a----       21/03/2017     12:11             42 sample2.txt
```

Ta da! There they are, back again.[^fnc]

[^fnc]:Why the -f, force, on the checkout command? Well, if you did it *exactly* as I have then the deleted files had not been committed. Git won't overwrite uncommitted changes without being made to! Generally it won't do anything that might lose data without being forced to. If you had first done a commit then once your status said 'nothing to commit' you could have just checked out a previous version (using its hash this time since 'master' - more technically HEAD - would be your most recent commit).

That method reverts you to the last thing committed - if you had done another commit in the meantime (like before you noticed your mising files) you would need to know the hash of the commit you wanted to check out, which you can get from **git log**. (I have done one more commit first just so that there is more than one entry to seedisplayed).[^fnd]

[^fnd]:if you just want to find hashes you might prefer **git status pretty=oneline**. Generally when supplying a hash to a command you only need to give enough to be unique, not the whole thing. With my example above **git checkout f86d5843** would be understood correctly.


```
> git log
commit 2160774336222861a1374bd9411610976974a2bc
Author: Ashley Oliver <ashley.p.oliver@gmail.com>
Date:   Tue Mar 21 12:18:54 2017 +0000

    Restored files

commit f86d5843102226b12770f1623e9a67186fcfcf24
Author: Ashley Oliver <ashley.p.oliver@gmail.com>
Date:   Tue Mar 21 12:10:41 2017 +0000

    Initial commit
```

You can do much, much more -- revert changes to individual files for instance, find the differences between two files, many other things
There is a lot of excellent [documentation](https://git-scm.com/doc) out there for Git. You should, *really should*, think about creating an account for yourself on GitHub. You may also want to install a GUI for Git - although, as usual, you can actually do more with the command line once you have learned to use it.

**Basic git functionality is integrated into Visual Code.**
 See the icon on the left hand side. Learn to use it. Really. Learn [here](https://code.visualstudio.com/docs/editor**/versioncontrol).
 Git is also fully integrated into Visual Studio, although less obviously and intuitively.

### Alternative method of getting starting, explicit remote
An alternative is to start by creating a an empty repository *remotely*, say on OneDrive, clone it locally, to give yourself an empty local repository and then start adding files to it. This sequence would look as follows. Note the way local paths are specified and obvioucly adjust to suit your system. **This assumes that the OneDrive dekstop support is present so that you have  a local folder being mirrored.** The commands would be
```
cd E:/Users/Sys/OneDrive
mkdir gitrepo
cd gitrepo
git init --bare
cd C:/Working
git clone file:///E:/Users/Sys/OneDrive/gitrepo .
```
E:/Users ... and C:/Working ... would be paths on your system, gitrepo is just a name and watch the triple '///' and the '.' in the last line.
.

## Using a Remote

### First time only

+ you will need to create an account on GitHub

Your GitHub username - `<uname>` and password - `<pwd>` will be needed below.

Tell your local git instance how to tag new commits

```bash
git config -g user.name "<uname>"
git config -g user.email "<email>"
```
it is probably best to use the same email as you used in creating your GitHub account. The -g makes this a 'global' setting for git on your local machine, leave it out if you only want it to affect this workspace (only likely if you routinely use several different GitHub accouns in which case you would already know that). 

If you did create a private repo read [Troubleshooting 1](#troubleshooting) before continuing ...


+ create an empty repo on a remote fileserver accessible via URL. 
	
	For GitHub this means press the 'New' button, come up with a name for the repo, possibly (depending on your account type) select Private/Public (use Public by default), you want an empty repo so do not check any of the boxes.

	Copy the repo url it wil be something like `https://github.com/<uname>/<repo>`

> Logging in to GitHub
>
> Before we can make changes we will need to be authenticated and authorized to do so. Currently there are two ways this can be done whether at the command line or in Visual Code. You can authenticate using the web site (simple, once, but you have to do it __every__ time you make a change, gets old, quickly) or using a Personal Access Token (more to think about the first time, but once only). To create a PAT, find Settings - it's in the dropdown from your profile/account icon in the top right of your dashboard). Now scroll down until you see `Developer Settings' in the left side menu (it is near the bottom). On the next screen, select 'Personal Access Tokens' in the left menu.

+  Back in a Visual Code terminal 
	
	`git remote add origin <url>`
+ and then 

	```git push origin master```
	
	('origin' is just a name, but is what we commonly call the remote repo. 'master' is just a name but is what the local branch will be called unless you have changed it)  

Visual Studio Code supports a simple 'sync' command, as do many other IDEs, (the little circular two-arrow icon bottom left) but to sync manually after future changes you could ...

+ make a local commit
+ ```git fetch origin```
	 (not needed if you are sure there are no changes in the remote, which would usually be the case if you are the only person using the repo)
+ ```git push origin master```	 

### Workflow with a remote

Almost the same

+ Commit files that have changed since the last commit **git add**  and then **git commit** at the command line.

	If using Visual Code, all changed files wil be added to your commit by default, so all that is necessary is select the git action tab, enter a commit message and hit the 'tick' icon.

+ Sync with the remote. Technically you should do a **git pull** and then a **git push** but if you are the only user and you have changed nothing directly on GitHub then the 'pull' is unnecessary.

	If using Visual Code just hit he sync icon bottom left in the status bar (circular, two arrows)

That's it. 



#### Troubleshooting

1. If your repo was private you may get 'repo not found' when you push. This is because your local machine does not have write access to the repo. If you had already added the remote, remove it

	```git remote rm origin```

	then re-add it but this time including your GitHub credentials

	```git remote add origin https://<uname>:<pwd>@github.com/<uname>/<repo>```

2. If you are behind a corporate firewall of the "I am going to forge certificates so that I can snoop on your encrypted communications" type, you may get authentication errors when using https. Try this to fix it

	```
	git config -g http.sslVerify false
	```




> Original version of this document written with [StackEdit](https://stackedit.io/).

