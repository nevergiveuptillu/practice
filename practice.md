# Commands:
- 3 areas of working -- Working tree
                     -- Staging area
                     -- Local repository
- git init: (Intialize a new repository)
----------
- git init
- PS D:\git> git config --global user.name "shivasomanath"
- PS D:\git> git config --global user.email "shivasomanath7@outlook.com"
- git status: shows the status of working tree and changes
-------------
- git status  >>> Red -- Working tree
- git add: add the changes to working tree to staging area
---------
- git add one.txt  >>> Green -- Staging area (opened cotton box)
- git commit: this command commits the changes from staging area to repo
------------
- git commit -m  "message" >>> Local Repository (Closed Cottonbox)
  - every commit given own info 
      - Commit Id
      - username
      - mail
      - message 
      - date time information
- git log : shows the commit inforamtion 
------------
- git log gives the information of commit
      - Commit Id
      - username
      - mail
      - message 
      - date time information
- git add . -- all changes to staging directory 
- git log --oneline
- HEAD -- what is the working tree is showing while working with git 
- git allways shows the latest commited info 
- git log(one space) : information of older commits
- git checkout commit id - we can move present to past && past - present
- git checkout master
- master :allways shows the latest commit
- git never understand folders allways deals with files
- git add . -means current directory changes 
- git add -A (or) git add --all >> 
- add with 4---
     - git add <file.path>
     - git add . (current directory)
     - git add -A (All )
     - git add -u (only modified files)
- touch {1..100}.txt
- git rm --cached test/somanath.word (staging area to working tree untracked)
- git restore --staged 1.txt (restore the file add sessions)
 - removing changes from working tree 
  Working tree 
    - modified  
       - git restore 
    - untracked
       - git clean -fd (all the untracked files are removed at a time)
# Branches:
-----------
 - Every git have a Default branch called as --Master
 - branch will always refers to the latest commit is working tree looking at
 - Head pointer we can move use moving checkout command
 - git branch:
 - $ git branch maina : when u are using the 1st creation of branch existed branch and present created branch points the latest commit
 - * shows the cuurent branch
    - $ git branch
       -   maina
       - * master
      understanding branches -- 
 - Merging:
 ----------
 - fastforward merge changing master
 - cherrypick - picking one of the commit
 - three way erge - 2 parents
 - rebase --changind the parent
- $ git checkout -b develop  >> create a new branch and move the head in to the branch
- to understand git 
  - plumbing commands
     - git cat-file -t <commit-id> type of commit
     - git cat-file -p <commit-id > content of commit
- hashes same when content is same
- sha 215 very stronger hashing
- Git refrence objects
   - branch 
   - tag
- branch is a reference object points the commit id and points the new commitid when a new commit happens
- tag also points the commit id when its created and does not move with new commit
- tag moves to another commit byt manually we need to move it
 - git cat-file -t <commit-id>
 -----------------------------
- $ git cat-file -t develop
commit  

>> only type showing (-t)

- git cat-file -p <commit-id >
------------------------------
$ git cat-file -p d795fa9
tree 19d50ab9d00e8662bfc1636a33cbe0ab86e60037
parent 03c3d1589dba085831f65eaa82d53d9da34b1c7c
author shivasomanath <shivasomanath7@outlook.com> 1689749857 +0530
committer shivasomanath <shivasomanath7@outlook.com> 1689749857 +0530

update docs

>> shows the content of commit (-p)   blob means file
    - tree: tree is the structure which commits are done by us

    $ git cat-file -p 19d50ab9d00e8662bfc1636a33cbe0ab86e60037
   - 040000 tree cc209bbb131bd621a30edcd1299a013d8476d51d    docs
   - 040000 tree 93bec393ec5b159cb4befb8545b68bfd266cf1c6    src
   - 040000 tree 5acbdb00471ee1794a89ef92ccbd6f61c5e506a4    test
   -     
    - parent : which os top of that commit the parent indicates immediate older commit
    - author: who is the created the commit 
    - commiter: who is done the commit
    update docs: message --the changes done by us
--- git stores properatary formate
- every commit changes time and working tree updated
- git based on hashes - content 
- git (global inforamtion tracker)
Merging Changes:
---------------
- merge conflict : dirrerent contions apply when the merging is started is caller merge confilct 
- $ git merge develop
-----------------------
Auto-merging src/main.py
CONFLICT (content): Merge conflict in src/main.py
Automatic merge failed; fix conflicts and then commit the result.

- Unmerged paths:
- $ git commit
[master 1017107] Merge branch 'develop'
- megred
--------
$ git log --oneline
1017107 (HEAD -> master) Merge branch 'develop'
- threeway merge  merge
--------
$ git cat-file -p 1017107
tree c4d98ca2ce33dcdbe2f9f1341644603190c4814f
parent 85eee2ec78aa1ece90d8ddbc34b58bda127bbdba
parent 93034c2976692da86f4835defc581226176b1678

fast forward merge:
-------------------
- with out changes in master(which is parent) branch this merge will applied
- 
```
DELL@Somanath MINGW64 /d/git/reference/howgitworks (master)
$ git merge develop
Updating 03c3d15..17bcc93
Fast-forward
 docs/readme.md | 4 ++++
 test/main.py   | 2 +-
 2 files changed, 5 insertions(+), 1 deletion(-)

DELL@Somanath MINGW64 /d/git/reference/howgitworks (master)
$ git log --oneline
17bcc93 (HEAD -> master, develop) under
d795fa9 update docs
03c3d15 added statements
5228a43 added folder structure
```
merges are directly moved to pointers to latest in develop branch because no changes are done in master is caller fastforward merge
commit id : is included parent commit of commit
rebase merge:
------------
- $ git log --oneline --graph --all
* b374724 (develop) word
| * 488a126 (HEAD -> master) work
|/
* 17bcc93 under
* d795fa9 update docs
* 03c3d15 added statements
* 5228a43 added folder structure
- DELL@Somanath MINGW64 /d/git/reference/howgitworks (develop)
$ git rebase master
-------------------
Successfully rebased and updated refs/heads/develop.
- git 
- checked but not understanded
cherrypick:
----------
- pick one or sequece of commits
- $ git cherry-pick --continue
[master 24276cf] second
 Date: Wed Jul 19 16:13:34 2023 +0530
 1 file changed, 8 insertions(+)
 create mode 100644 mani/main.py

DELL@Somanath MINGW64 /d/git/rebaseconcept (master)
$ git log --oneline
24276cf (HEAD -> master) second
f133e47 2nd
d5b4aa2 1st
--
$ git cherry
cherry        cherry-pick

DELL@Somanath MINGW64 /d/git/rebaseconcept (master)
$ git cherry-pick 07f6ef6
CONFLICT (modify/delete): mani/main.py deleted in HEAD and modified in 07f6ef6 (second).  Version 07f6ef6 (second) of mani/main.py left in tree.
error: could not apply 07f6ef6... second
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state
```

git diff:
----------
- diffrence bw the commits 
- $ git diff 492be34..1a626a9 for >> showing after mentioned commit id details
- $ git diff 492be34^..1a626a9 >> show the diffrence of selected commit id

git show Head:
-------------
- $ git show HEAD
commit 1a626a9289350deccbad345c90bdf88168aaf7b2 (HEAD -> master)
Author: shivasomanath <shivasomanath7@outlook.com>
Date:   Thu Jul 20 11:58:26 2023 +0530

    5th

diff --git a/mani/main.py b/mani/main.py
index 0007172..7901de9 100644
Binary files a/mani/main.py and b/mani/main.py differ  
(inforamtion about head and diff b/w the error )
- $ git show HEAD~1 (show one commit back head postion)
- $ git show HEAD~2 (shows the 2 commits back head postion)

Interactive Rebase:
------------------
```
pick 24276cf second
pick 492be34 3rd
pick 0ffcf40 4th
pick 1a626a9 5th

# Rebase f133e47..1a626a9 onto f133e47 (4 commands)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name

```
```
work done


# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Wed Jul 19 16:13:34 2023 +0530
#
# interactive rebase in progress; onto f133e47
# Last command done (1 command done):
#    reword 24276cf second
# Next commands to do (3 remaining commands):
#    pick 492be34 3rd
#    pick 0ffcf40 4th
# You are currently editing a commit while rebasing branch 'master' on 'f133e47'.
#
# Changes to be committed:
#       new file:   mani/main.py
#
```
- reword 24276cf second
- pick 492be34 3rd
- pick 0ffcf40 4th
- pick 1a626a9 5th
- modify the name commit id 
- 
- $ git rebase -i HEAD~4
[detached HEAD 25ace39] work done
 Date: Wed Jul 19 16:13:34 2023 +0530
 1 file changed, 8 insertions(+)
 create mode 100644 mani/main.py
Successfully rebased and updated refs/heads/master.

squash:
------
- $ git rebase -i HEAD~2
DELL@Somanath MINGW64 /d/GiT/rebaseconcept (master)
$ git log --oneline --graph --all
* 7dd7c5c (HEAD -> master) 4 and 5
* 73437a9 3rd
* 25ace39 work done
| * 596a02f (maina) third
| * 07f6ef6 second
| * 055b52a first
|/
* f133e47 2nd
* d5b4aa2 1st

remove commit : drop commit
----------- ---
- git rebase -i HEAD~2 
- DROP FROM VI
- 
EDIT :
----- 
- Use for recall the commits 
- 
Rewrting Hisory:
---------------
change commit msg >> combine commits (squash) >> remove Commot (drop) >>edit commit (edit)

>> Git Amend:
------------
- git commit --amend by this we can change latest commit msg it will be aplicable where head is looking at 
- 

-- git commits on afile
-- git specific commit
-- find all the commits b/w some dates

4th area of Git (Remote Repositories)
----------------------------------
- Working tree  add staging area commit localrepo               RemoteRepo
               -----            --------          -------------
- any servers hosts git repos called as `git servers`
- many repos 
   - self hosted
     - gitolite 
     - git lab
   - cloud hosted (user managemnet and demon features)
     - Git hub
     - Bitbucket
     - Azure Source repos
     - Aws Code Commit

Self-hosted: Repository
----------
- git init --bare
LS  - config  
    - description  
    - HEAD  
    - hooks/  
    - info/  
    - objects/  
    - refs/

- git clone file://D:/GiT/gitserver/
- PS D:\GiT\local\git-server> git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 202 bytes | 202.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To file://D:\GiT\git-server
 * [new branch]      master -> master

---
Git Repository:
---------------
- git branch -M main (renaming branch)
- $ git remote add origin https://github.com/SHIVASOMANATH/practice.git (create a remote named as origin)
- $ git push origin main (push changes of origin to remote)
- ---
DELL@Somanath MINGW64 /d/GiT/practice2 (main)
$ git branch
* main

DELL@Somanath MINGW64 /d/GiT/practice2 (main)
$ git branch --all
* main
  remotes/origin/main
---
git branch -r (will show the remote branches)

-- fetch (remote behave like) 
-- merge (to local)
-- pull >> fetch + merge
 * branch            main       -> FETCH_HEAD
   179fe6c..a52aa80  main       -> origin/main
Auto-merging three.txt
CONFLICT (content): Merge conflict in three.txt

-- 
$ git log --oneline --graph
*   98c1322 (HEAD -> main, origin/main) Merge branch 'main' of https://github.com/SHIVASOMANATH/practice
|\
| * a52aa80 Update three.txt
* | 8c5c61f imp
|/
* 179fe6c some stuff
* eeac37d 3rd
* adf6665 second
* 528568e first
---
- $ git pull origin main --rebase (it wll be overite merge )
- $ git rebase --continue 

gitpull:
-------
- git pull :fetch+merge
- git pull rebase : this not leads extra merge commits

- ---  setup upstream:

$ git push -u origin main
Everything up-to-date
branch 'main' set up to track 'origin/main

git push --all origin

git push --all azdevops

git push --all aws

--

Tags:
---- 
- light weight tags 
- anotated tages 

- Detach Head :
---------------
- crate tag or branch  head moves
- we can move back back in time we cant change any thing
- git tag -a "int_dev_0.1" -m " this is development star" (-m message indicates)

- git rebase HEAD~2 drop
- logs:
   - reflogs permenent to our system
   - general logs
  - git reflog commit id 
  - git reset --hard commitid
  -- git done 
  

- 
Jenkins Installltion:
--------------------