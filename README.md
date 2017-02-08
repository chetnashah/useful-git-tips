
* Remember: git push <REMOTENAME> <BRANCHNAME>
* Remember: git pull <REMOTENAME> <BRANCHNAME>
* Remember: git rebase base-branch feature-branch 
( feature branch commits are moved on top of base-branch,
if feature branch is not specified, currently checkoud branch's commits
are moved on top of base-branch)
* git pull = git fetch + git merge
* Be aware of merge strategies
* Use git reset to unstage files
* use git revert to undo a commit by creating a new commit.
* Rewrite history/squashing/splitting only on feature branches.
* Instead of merging master into feature branch, keep rebasing feature
  on top of master
* Always use git cherry-pick with -n so it won't commit right away.
* see remotes with git remote -v
* Add remotes using git remote add <remote-nickname> <remote-url>
* When wanting to make changes to public projects/npm modules/libs etc
  fork that project and add remote upstream pointing to original, and
  don't modify your fork's master if possible
* use VScode for basic git mgmt if possible.
* P4 merge is awesome mergetool
* find problems in specific commits with git bisect

### Fork Management
* Fork on github - you will get yourusername/project
* Clone your fork to local machine
* Note: Your fork's clone will not have remote upstream (originaluser/project) setup, You have to set it up yourself as following
* Adding upstream remote :
  git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git

* Verify you have two remotes origin(your fork) and upstream(owner)
* git fetch upstream, this will bring upstream changes to local upstream
* now two things u can do with current master, checkout current master,
    git merge upstream/master or
    rebase master on top of upstream/master
    i.e. git rebase upstream/master
