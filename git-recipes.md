# Learn Git in 10 Minutes

This document is a one-page Git for beginning users and for users who
want to quickly lookup a command or workflow. It is not supposed to be
an exhaustive guide, rather a guide that provides essential commands
and concepts to get started the right way.

## The Magic of Git
Decentralized collaboration
Fast, flexible.
## Intro, key concepts
### Key Concepts
Every git repository can be used for check-ins.  Among other things, this means you can check out a branch sitting on another developer's machine which does not exist on github.

### Distributed version control system
### Workflow
Pull (fetch + merge) or Checkout / update => (do some work) => stage
=> commit locally => push to server

## Typical workflow
### Cloning an existing repository
### Creating a new shared repository on a server
- On the server
First create a standard repository on the server:

    $ pwd
    /srv/git
    $ git init myproject
    user$ cd myproject
    $ echo 'README' > README.md
    $ git add .
    $ git commit -m "initial commit"

- Then create a bare repository

    $ git clone --bare --shared myproject myproject.git

The shared option ensure Git adds group write permissions.
- On the client

    user@clientmachine$ git clone username@server.com:/srv/git/myproject.git

modify a file

    $ echo hello >> README.md
    $ git add README.md
    $ git commit -m 'added demo string'
    $ git push
- 
## Typical commit workflow
### Long running feature development model
### Tag for versionning
## Essential commands
## git commit

    $ git add .
    $ git commit

or 

$ git commit -a
** git fetch
    
    $ git fetch
    Get changes from server
    ...
    From ssh://git.metadot.com/srv/git/project
    ace4e1e..9bf4acf  master     -> origin/master

See merge command to merge changes or pull command to fetch and merge in one command
## git diff
Shows differences

    $ git diff origin/master
    diff --git a/README b/README
    index b55010d..b1a1441 100644
    --- a/README
    +++ b/README
    @@ -5,5 +5,4 @@ Thank you.
     -- supercobra was here
     -- supercobra from home was here.
     -- logan was here.
    --- supercobra was here.

## git merge

    $ git checkout master
    $ git merge abranch
    $ git merge i18n
    $ git merge origin/master

## git config

    $ git config --list
    user.name=supercobra
    user.email=daniel@metadot.com
    core.repositoryformatversion=0
    core.filemode=true
    core.bare=false
    core.logallrefupdates=true
    core.ignorecase=true
    core.precomposeunicode=false
    remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
    remote.origin.url=supercobra@git.metadot.com:/srv/git/bam.git
    branch.master.remote=origin
    branch.master.merge=refs/heads/master
    
- Important files:
/etc/gitconfig and /.gitconfig, f


## git branch

    $ git branch name

Create a branch and use it immediately

    $ git branch -r i18n
    $ git branch -r

Useful

    $find .git/refs

### shows all branches including remotes

    $ git checkout master
    $ git branch abranch
    $ git checkout abranch

## git rebase
## delete branch

    git branch -D name
==
    git checkout -b bigfeature master

## git checkout
## remotes
add Bob's repo and more repos of the same project
## git push
Push changes from local repo to remote (called orgin by default):
    $ git init <alias> <local_branch>
    $ git push origin master

Push changes of branch i18n to remote

    $ git push origin i18n

## git fetch
use git fetch to 'update'

## git pull
Wrapper for fetch and merge.

## git log
head by default
    git log --oneline
    git log i18n --oneline
    git log --online --graph
    git log --oneline --all --graph --decorate

    git log -p 
    
shows patch

    git log --stat
    git log --stat --no-merges

### tips
#### List config
 
    $ git config -l
    alias.dog "log --decorate --oneline --graph"

#### Log

Create a visual log

    $ git config --global alias.dog "log --decorate --oneline --graph"

    $ git dog
     * 6265cc6 (HEAD, origin/master, origin/HEAD, master) Update learngitin10min.org
     *   a3d292b Merge branch 'master' of https://github.com/supercobra/learngitin10min
     |\  
     | * 9d0d836 More improvements...
     | * 4d2e94b Improved.
     | * d76784e Recreated from scratch.
     | * eb4a11c Typos.
     * | 4f09974 some more things...
     * | affda74 Improved.
     * | c21a119 Recreated from scratch.
     |/  
     * 6e2dfa1 Update README.md
     * e6c8788 Initial commit

### log subset

    git log branchA ^branchB
or 
     git log branchB ..branchA
     
show commits reachable by branchA that are not reachable by branchB

    git log i18N ^master
    
changes in branch i18N not in master

After doing a fetch: show incoming changes (not merged yet).

    git log origin/master ^master

    git log master ^origin/master

show outgoing changes not pushed to the server yet.

## git tag
### creating tag

    $ git tag -a v1.4 -m 'my version 1.4'
    $ git tag
    v0.1
    v1.3
    v1.4

### pushing a tag

You need to explicitly push tags

    $ git push origin v12.1

## Ignoring files

    $ cat my-config.conf >> .gitignore

# Resources

## Getting help

    $ git help <command>
    $ git <command> --help
    $ man git-<command>

### Links

* http://git-scm.com
http://gitref.org
http://progit.com
chacon@gmail.com

### Video: Introduction to Git with Scott Chacon of GitHub
http://www.youtube.com/watch?v=ZDR433b0HJY


## Suggested Branching Strategy

* All major work is done in branches.
* It is up to the developer to keep each branch up-to-date with changes in the master branch.
* When testing is done, it is up to the developer to pull their changes into master and resolve any conflicts.

## Git Commands for Different Stages

### You're Beginning a New Task

    git branch yourname_somedescr_optionaldate (e.g., "git branch jason_fixPartyTimeBug")
    git checkout yourname_somedescr_optionaldate

Now change some code!

### You altered file ABC.txt and will commit it later
    git add ABC.txt

### You have changes to commit
    git commit

### You want to push the changes to the server

    git push origin yourname_somedescr_optionaldate

There are some shortcuts and assumptions git will take, but this is a verbose way to ensure that your branch is going to the right place.  Once you're positive you are pointing to the right remote and you're on the right branch, a simple 'git push' will do.

### You are working on yourname_somedescr_optionaldate and you want to pull in the latest change to master

    git pull origin master

The same note from above about git push applies to git pull.

### You're done working on your branch and it's time to pull it in to master

    git checkout master
    git pull origin master
    git pull origin yourname_somedescr_optionaldate

