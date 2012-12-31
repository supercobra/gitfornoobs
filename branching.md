## Suggested Branching Strategy

* All major work is done in branches.
* It is up to the developer to keep each branch up-to-date with changes in the master branch.
* When testing is done, it is up to the developer to pull their changes into master and resolve any conflicts.

## Git Commands for Different Stages

### You're Beginning a New Task

+ git branch yourname_somedescr_optionaldate (e.g., "git branch jason_fixPartyTimeBug")
+ git checkout yourname_somedescr_optionaldate
+ Start changing some code!

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

+ git checkout master
+ git pull origin master (to get it up to date)
+ git pull origin yourname_somedescr_optionaldate

