

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