* Git Recipes
** Getting started with Git
** Starting w/ repositories
*** Creating a new local repository

$ cd myproject
$ git init
Create the repository files.
$ git add *.java
$ git add README.md
$ git commit -m 'initial commit'

*** Cloning an existing repository
$ git clone https://github.com/supercobra/coolproject.git

This creates a coolproject directory with all project and git files.

*** Creating a server repository to push to
On server
$ git init --bare myproject.git

On workstation

** Adding files
** Commiting files
** Pushing to repository
$ git push origin master
Counting objects: 440, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (412/412), done.
Writing objects: 100% (440/440), 29.90 MiB | 75 KiB/s, done.
Total 440 (delta 39), reused 0 (delta 0)
To git.metadot.com:/srv/git/daskeyboard_website
 * [new branch]      master -> master
** Working with remotes 
*** Listing remotes
$ git remote -v

*** Adding a new remote
$ git remote add supercobra-dartstrap  https://github.com/supercobra/dartstrap.git
*** Pushing local master to new remote
$ git push supercobra-dartstrap master

*** Inspecting a remote
$ git remote show supercobra-dartstrap
 * remote supercobra-dartstrap
   Fetch URL: https://github.com/supercobra/dartstrap.git
   Push  URL: https://github.com/supercobra/dartstrap.git
   HEAD branch: master
   Remote branch:
     master tracked
   Local ref configured for 'git push':
     master pushes to master (up to date)

*** Delete or renaming a remote
$ git remote rm <name>
$ git remote rename <old> <new>

** Advanced Git techniques
*** TODO Reset
*** TODO Staching
*** TODO Long running branches
