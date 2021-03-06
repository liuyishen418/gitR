Git and Github
================

### Common git commands

git init

git status

git add -A

git commit -m “message”

git commit –amend –no-edit

git pull

git push

git reset –hard HEAD^

git push –force

git remote -v

git branch -vv

git remote rename origin upstream

git remote add origin xxxx

git branch -d branchName

git push origin –delete branchName

### Scenarios

#### scenario 0: start a new project

  - create a new repo on github;
  - start a new project with version control option, add the remote url;
  - if project already there on Rstudio, then try git clone or git
    remote add

#### scenario 1: work in progress

  - keep doing the following:
      - git commit -m “WIP”
      - git commit –amend –no-edit
  - when done:
      - git commit –amend -m “serious message”
      - git pull
      - git push

#### scenario 2: collaborator made changes to remote

  - git pull
  - resolve manually any conflicts
  - git add -A
  - git commit –amend –no-edit
  - continue work from there

#### scenario 3: go back to the most recent commit, and discard the current state

  - git reset –hard HEAD^
  - then work from there

#### scenario 4: add new features;

  - git checkout -b feature-1
  - continue work on this branch, when ready
  - git checkout master
  - git merge feature-1
  - git add -A
  - git commit -m “feature 1 merged”
  - git pull
  - git push

#### scenario 5: fork-and-clone;

  - fork duplicates the repo on your own account, clone only downloads
    the repo to local PC, close also allows you to track evoluation in
    the target repo, pull request is a github function, not git command;

  - fork a repo owned by others on Github;

  - create new project to the forked repo owned by you;

  - create new branch and work on it;

  - forked repo is remote origin, original repo owned by others is
    remote upstream;

  - pull from remote upstream on master branch to get up to date, the
    option fast-forward merge makes sure that if you made changes to
    local master branch an error shows up;
    
      - git pull upstream master –ff-only

  - when done, make a pull request on Github;

  - side note: if you made changes to local master and cause a pull
    fail:
    
      - git checkout -b newBranch \# for saving the modified local
        master;
      - git checkout master
      - git reset –hard ShAname \# shaName for the commit that local and
        upstream agree;
      - git pull upstream master –ff-only \# bring local master up to
        date;

#### scenario 6: make or accept PR

  - read instructions online, such as [this
    one](https://yangsu.github.io/pull-request-tutorial/)

#### scenario 7: regret commit on local machine

  - git reset –hard HEAD^ \# go back to previous commit, and delete all
    updates from there to now;
  - git reset HEAD^ \# go back to previous commit, keep new changed
    files, and unstage them;
  - git reset –soft HEAD^ \# go back to previous commit, keep new
    changed files, and keep them \# staged;

#### scenario 8: collabrate on a single repo

  - git pull origin master (make sure local master is up to date);
  - git checkout -b newFeature (create a new branch to work on the
    changes);
  - git push origin newFeature (push the new branch to remote);
  - make a pull request on Github from newFeature to master;
  - go back and forth to make newFeature suitable to merge;
  - when done, merge newFeature to master on Github or local PC;

### Github tips:

  - press “t” to open file search;

  - press “y” to get permanent link;

  - send people downloadable links to your repo, add
    “/archive/master.zip”
    
      - for example,
        <https://github.com/liuyishen418/test/archive/master.zip>
