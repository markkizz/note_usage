# How to use git

## Git command
- `git checkout HEAD {filename}` : __undo__ a change in staged __not in commit__ (git add)
- `git diff` : show the differrent your __modified__ what you change in your source code (__operates in working directory only!!__)
- `git diff --staged`: show the different your modified in __staged area__ what you change in your source code
- `git show HEAD` : In Git, the commit you are currently on is known as the HEAD commit. In many cases, the most recently made commit is the HEAD commit. --The output of this command will display everything the git log command displays for the HEAD commit, plus all the file changes that were committed.
- `git checkout HEAD^`: This is command will take you to previous commit and do anything what you want (`HEAD` is your pointer and `^` is 1 step backward to previous commit or you can use ~{num} represent to number of step that you want to use)
- `git branch -f master HEAD~3`: moves (by force) the master branch to three parents behind HEAD. (One of the most common ways to use relative refs is to move branches around. You can directly reassign a branch to a commit with the `-f` option.)
- `git branch -f master {numCommit}` : to force master point to the other commit
(git branch -f master C6;git checkout HEAD~1;git branch -f bugFix HEAD~1)
<!-- push -->
- `git push -u origin branch_name` - push and tell git to remember what I have push
<!-- pull -->
- `git pull origin {branch_name} --allow-unrelated-histories`: to sync with server-side when file in both side not the same and can't pull from server-side
- `git rm --cached {file}` : if you add the wrong file you can remove that file with this is command

## Fixing Common Mistakes and Undoing Bad Commits
- `git checkout {file name}`: to undo change in file
- `git commit -amend -m "{message}"`: change message in commit



## change git remote repository
when you clone the other repository without forking. You should try this:
1. `git remote -v` : this command tell you about what is a repository you remote to
2. `git remote rm origin`: this command will kill a current remote repository
3. create your repository in your git hub and copy a clone url
4. `git remote add origin "clone-url"`: this command will change to your own repository
- Now you can push/publish to your repositiry and commit them

----> Create fork it a easy way too <----
- it not remove a history!

## Git merge
### Fast-Forward merging
- when we change something in branch and commit it, but on master branch we didn't change anything and merge branch that we change. it turns out the master branch will go through without hitch. This is called a __fast-forward merge__

before
|sad09|---|as342|--|Bsae80|--|io234|(master)--|asir12|(branch)<br>
after
|sad09|---|as342|--|Bsae80|--|io234|--|asir12|(master),(branch)

### Normal merge(Merging divergent branches)
- when we change something in master and branch and commit it then merge into master. Our new merge commit, has both the last commit from master and the commit we made on the other branch as it's parents

## Git rebase
What rebase will do is take all of the commits on your feature branch and move them on top of the master commits __or__ rebase the up to date of master branch in remote repo to make sure that in my local repo is synced to the latest commit from remote master.
- `git rebase {branch name that you want}`

## Git reset and Git revert (undo the commit)
There are two primary ways to undo changes in Git -- one is using `git reset` and the other is using `git revert`
- `git reset` : reverts changes by moving a branch reference backwards in time to an older commit. This  command will move a branch backwards as if the commit had never been made in the first place
- `git reset --soft {commit hash}`: reset commit that you want

While resetting works great for local branches on your own machine, its method of "rewriting history" doesn't work for remote branches that others are using

In order to reverse changes and share those reversed changes with others, we need to use git revert.

## Git stash
if at any point you have local changes that you do not yet want to put into a commit, or want to store somewhere while you try some different angle to solve a problem, you can __stash__ those changes away
(like a draft a picture then keep and draft a new picture with another ideal). A git stash is basically a stack of changes on which you store any changes to the Working Directory(last stash is index 0).
- `git stash`: save the current code and go back to lastest commit
- `git stash list`: list the all of stash that you save
- `git stash apply {index-number}`: fill the code that we have save change in stash but not remove from stash lish
- `git stash pop`: which takes the latest change that was stashed and applies it the to the Working Directory again and remove from stash list

Manipulation of older stashes:
- `git stash push -m 'stash-description'`

Deleting stashes:
- git stash drop + index-number

Choose a stash to implement:
- git stash pop + index-number

When we don't need stashes anymore:
- git stash clear

## Git cherry-pick
- `git cherry-pick {commit hash}`: to pick the commit from other branch that you want to commit in currently branch
