# Git For Noobs

This document is a one-page Git for noobs. It is not supposed to be
an exhaustive guide, rather a guide that provides essential commands
and concepts to get started the in no time.

## The Magic of Git
Decentralized collaboration. Fast, really fast. Flexible.

## Intro, key concepts
### Key Concepts

You **add** then **commit** your files locally then **push** changes to the server. Sometimes, you **merge** server updates back to your local repository.


Advanced: You can merge and push to many different remotes. This means you can check out a 
branch sitting on another developer's machine which does not exist the server.

### Working With a Centralized Git Repository
This is a typical way an organization will work: one central shared Git project. Developers get and push changes from and to the server.

1. On your workstation: clone the project
To be done only once:

  	git clone git@github.com:supercobra/learngitin10min.git
		
2. Make changes

		vim for_life.txt
		
3. Commit your changes to your local repository

		git commit file1 file2 file3 -m "Some message"
		
5. Test, test some more, test some more more.

6. Get the lastest code on the server and merge it with you code ("the server" is also known as "origin")

		git pull
		
5. Test, test some more, test some more more, fix and commit changes.
		
6. Push your changes up to the server

		git push
		
7. Repeat! Go to step 2.

### Working with several remotes
In some cases your local config may have multiple "remotes", so you'll need to specify the remote you want to use when pushing and pulling.  Often, these are what you want:

		git pull origin master
		git push origin master

		git pull origin jasons_amazing_branch
		git push origin daves_equally_amazing_branch

Not sure where 'origin' points?

		git remote show origin


### Creating a shared repository
Here is how to create a shared Git repo where people can pull and push from.

- On the erver
First create a standard repository on the server:

		ssh user@example.com
		mkdir myproject.git
		cd myproject.git
		git init --bare
		
- On your local workstation
Assuming the myproject directory has the content ready:

		cd myproject
		git init
		git add *
		git commit -m "Initial import"
		git remote add origin user@example.com:/path/to/myproject.git
		git push -u origin master

    
## TBD How to work with a long running feature development model
## TBD Tag for versionning
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
    $ git merge mynewfeature
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
    
### Important files:
- /etc/gitconfig and 
- ~/.gitconfig
-   In your local repo, look at .git/refs/<all files>

### git branch

    $ git branch name

Create a branch and use it immediately

    $ git branch -r myexperiment
    $ git branch -r

### shows all branches including remotes

   tbd

## git rebase
## delete branch

    git branch -D name

## remotes
Add Bob's repo and more repos of the same project

## git push

Push changes from local repo to remote (called orgin by default):

$ git push origin master

Push changes of branch myexperiment to remote

    $ git push origin myexperiment

## git log
head by default
    git log --oneline
    git log i18n --oneline
    git log --online --graph
    git log --oneline --all --graph --decorate

    git log -p 
    
## shows patch

    git log --stat
    git log --stat --no-merges

### tips
#### List config
 
    $ git config -l
    alias.dog "log --decorate --oneline --graph"

#### Log: a visual log using a cool alias
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

## Getting help

    $ git help <command>
    $ git <command> --help
    $ man git-<command>

### Lean More Links

- http://git-scm.com
- http://gitref.org
- http://progit.com

## Video: Introduction to Git with Scott Chacon of GitHub

- http://www.youtube.com/watch?v=ZDR433b0HJY


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

