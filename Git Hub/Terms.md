- Regression
- api testing
- unit test
- day & night build
- quality gate
- artifacts-
- Repository

# Day2
------
- system test
- Performsnce
- security
  - Weekly build
  - UAT ( user Acceptance Test)
- Sprint build
- Tools: 

# Day3
-------
- Git  
 - Vcs client >> Vcs server >> Devoloper repos  ( client server version controle system ) ---- Bit keeper
   - single system vcs
   - client server vcs
      - online
      - offline (svn)
   - Distributed vcs
      - mercurial
      - git
    deamon-- which is runs all the time background still server up 
      - http
      - ssh
    git hub - server which maintain repositries and server some demons running hosting is called git hub which is cominicated with 
    git - individual machines which are present git repos called git  distributed version controll system

     - so called servers
     - very simple content tracker
  
  - working tree(directory) >(add)> Staging Area (Cache area) >(commit)> Local Repos > > remote repos >> stash
    - git maintain history og commits
    - 

GIT:
----
  - working tree(directory) >(add)> Staging Area (Cache area) >(commit)> Local Repos > >
    - git status  >> green staging area >> red open area
    - git add
    - git commit -m "seal the box"
    - 
### Terms

- Dev SecOps
- scrum
- Neight -build
- infraprovisiong
- tee command
- standardinput - standard output
- fast forward much
- Hashing
- 
- 

Right now understanding words
- Repository
- agile-methodology
- waterfall model
- apt update /yum update
- 
- 
- 



# 11 -07-2023
-------------
- repository
- changes understanding
- graphs
- checkout
- branch
-- git init
-- git clone 
- add .
- status 
- commit -m ""
- pushub
- git log
- git checkout master devolop
- three- way merge
- merge commit 
- rebase : changing the parent
- cherry pick : select individual commit from regual bases commits
- fast forward merge
- 
# 12-07-2023 
------------
- how git works
----------------
-  tracker
- understand git plumbing commands 
  - git cat-file -t <commit -id> type
  - git cat-file -p <commit -id> contents
- integrity verification (hashing use )
- git uses - sha1 (algorithm )
- hash is unique number system
- sha256 strong and mostly using algorithm
- git log will dispaly the hashing 

- Git reference object (they dont have content they are points some thing)
  - branch (points to a latest commit )
  - tag (points to a same commit id as we are search )
  - 
- git cat-file -t <commit -id> type
- git cat-file -p <commit -id> contents
  - tree
  - parent
  - author
  - committer
       - tree 
          - src
          - docs
          - test
- propretary formate
- same content - same file stored ones
- checkout regenrate the working tree
- content tracker --  file system -- linus torwards
- git - global inforamtion tracker
- chekout moves the head
Merging --branches
--------------------
- merge -conflict (unable to decide change by git )
- 3 way merge
- fast forward merge
- .git / .objetcs

Git remote
---------------
* Remote-Repo
Self -hosted
  - Gitolite
  - Git -lab
  Cloud-based
   - Bit Bucket
   git >>>> origin/main
   fetch+merge
   (pull) 
   - git rebase use >>> 
   - name of remote and branch required pull & push
   - set default
   - git push -u origin main  upstream branches
   - git pull --rebase
   - git clone by defaults sets the upstream branch
   -  
Activity:
-------
   - code commit
   - azure Devops
   - bit bucket
   - git lab
Tag -
---
  - tag to apply to commit 
  - refs >> heads >> tags >> 
    - tag+commit = light weight  
    - anotated tags = messages >> 
 - tag neves moves it self

Detach head state:
-----------------
  - git switch 
  - create branch or tag while doing things
  - 
  - logs
    - git logs (  )
    - ref logs (maintain every thing) (permenent to ur system)
    - every local repositry have own 
    - grabage collection 
    - 

git rebase -i head
recover the commit deleted
- 