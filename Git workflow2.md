* Starting with Git
** Starting w/ repositories
*** Creating a new local repository

$ cd myproject
$ git init
Create the repository files.
$ git add *.java
$ git add README.md
$ git commit 'initial commit'

*** Cloning an existing repository
$ git clone https://github.com/supercobra/coolproject.git

This creates a coolproject directory with all project and git files.

*** Creating a server repository to push to
On server
$ git init --bare myproject.git

On workstation
* clone the repository
$ git clone bob@server.com:/path/to/myproject.git

** Add files
** Commit files
** Push to repository
$ git push origin master
Counting objects: 440, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (412/412), done.
Writing objects: 100% (440/440), 29.90 MiB | 75 KiB/s, done.
Total 440 (delta 39), reused 0 (delta 0)
To git.metadot.com:/srv/git/daskeyboard_website
 * [new branch]      master -> master
