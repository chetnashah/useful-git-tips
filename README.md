
* Use liquid prompt in shell to get status
* Renaming while cloning: `git clone <RepoUrl> <DestinationDirectory>`
* Remember: git push REMOTENAME BRANCHNAME
* Remember: git pull REMOTENAME BRANCHNAME
* Remember: git rebase base-branch feature-branch 
* Remember: git merge otherbranchname : merges otherbranch into currently checkouted branch.
* ( feature branch commits are moved on top of base-branch,
if feature branch is not specified, currently checkoud branch's commits
are moved on top of base-branch)
* git pull = git fetch + git merge
* Be aware of merge strategies
* Use git reset to unstage files
* use git revert to undo a commit by creating a new commit.
* Rewrite history/squashing/splitting only on feature branches. Do not rebase pushed/public  branches because this rewrites history for other people working on the project.
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
* see git reflog output regularly.

* updating your topic branch depending on master
```
git checkout topic          # current branch should be topic
git fetch origin            # Updates origin/master
git rebase origin/master    # Rebases current branch onto origin/master
```

### Remote details

* Read more at (https://git-scm.com/book/en/v2/Git-Branching-Remote-Branches)

* Anytime we git clone, tracking is setup for master branch to track origin/master.
* Remote branches are always named as following: REMOTENAME/BRANCHNAME e.g. origin/master.
* remote branches REMOTENAME/BRANCHNAME are immutable changes. to work on them you have to make/checkout a branch that tracks REMOTENAME/BRANCHNAME. See next :

* If the branch name you’re trying to checkout (a) doesn’t exist and (b) exactly matches a name on only one remote, Git will create a tracking branch for you:
```
$ git checkout serverfix
Branch serverfix set up to track remote branch serverfix from origin.
Switched to a new branch 'serverfix'
```

* Note commands : git fetch/pull/push remote branch :
 - If you don't specify branch, all banches of the given remote are fetched/pulled/pushed.
 - If you don't specify branch and remote, all the branches of all remotes are fetched/pulled/pushed.

### Fork Management
* When dealing with forks/remotes directly, use smaller commands seperately e.g. fetch, merge instead of pull.
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

* To just sync your local master (you are not making any changes in master), do git pull upstream master.
* The changes are still only in your local master, So do not forget to
push to github (origin/master) by git push origin master

### Git configuration

* Your git configuration file (.gitconfig) usually sits in 
Home directory (~)

* You can add aliases to your .gitconfig which can be called with
git aliasname

```
git config --global alias.ls 'log --oneline'
```
e.g. now you can do $ git ls

* Another useful is to see last commit
```
git config --global alias.last 'log -1 HEAD'


