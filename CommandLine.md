# Git Bash Command Line

## COMMANDS FOR NAVIGATION

+ ls - list
  can take an argument of a folder name
+ start . 
  open file explorer
+ clear
  clears the terminal screen, fresh work area
+ pwd 
  print working directory
+ cd 
  change directory
+ touch 
  creates a file
+ mkdir 
  creates a directory
+ rm 
  remove
+ rm -rf removes a directory by recursive force flag

## GIT COMMANDS

+ git status
  very useful tool to show where you are with respect to repo
+ git init
  -avoid running when already within a repo folder 
  -check using git status after cd to directory
+ git add .
  -stages tracked changes in all files in the current repo folder/branch for commit
+ git add "<filename>"
  -stages tracked changes in the specified filename
git commit opens vim if no editor configured to enter required message
git commit -m "Message" allows for adding commit message without opening editor
git log displays all of repo actions
code . opens repo in VS code

Git Documents https://git-scm.com/docs

Atomic Commits - keep each commit focused on a single thing
this makes rolling back much easier

git config --global core.editor "code --wait" sets VS Code as editor with wait for commit message

git log --oneline important to keep first line of commit message as a summary overview
commiting with a GUI using GitKraken
git commit --amend only works on previous commit if no new commits, also allows change to commit message

any files that contain secrets can be added to a file at the root level named .gitignore
the .gitignore file is tracked but any files or directories listed in the .gitignore file 
will not be tracked

Rename master branch to main

LAST COMMIT BEFORE BRANCHING

BRANCHING COMMANDS

git branch shows all branches
git branch branchName creates a new branch no spaces and meaningful name
git switch branchName
git checkout does more than git switch
git switch -c creates branch and switches in the same Command
git checkout -b is same as git switch -c 
git branch -d deletes branch if merged cannot be on the branch to delete
git branch -D force deletes if not merged use carefully cannot be on the branch to delete
git branch -m renames a branch must be on the branch to rename

MERGING
git merge HEAD must be on the branch to merge to. (fast forward merge)
merge conflicts will arise if separate changes to the same file such as a line deleted
in one branch and changed in another branch cannot be automatically resolved. Correct
conflicts to the file and remove the conflict markers to complete the merge. 

git diff compares unstaged changes with working directoy designating a and b. 
a is usually the working directory. a is identified with - and b with +
context included shows the starting row and number of rows in the context for each side.
deletions are indicated in red. insertions are indicated in green.

git diff HEAD shows staged or unstaged changes since last commit
git diff --staged or --cached shows changes in staged already
git diff HEAD filename limits display to specified filename
git diff --staged filename limits display to specified filename
git diff branch1..branch2 shows difference between specified branches
git diff commit1..commit2 (use hash identifier) shows difference between specified commits

git stash saves changes that you are not ready to commit so that you can move to a different branch
there can be multiple stashes if you use apply instead of pop this also lets you apply a stash in different branches.
git stash pop removes most recently saved changes from stash and applies them
git stash list shows what is in the stash the message refers only to what was last commit
git stash apply stash@{0} is an index used to apply a particular stash
git stash drop stash@{0} removes that index from the stash


git checkout commit hash - detached HEAD state, allows to inspect file(s) at a particular
commit or create a new branch from a point in the past

git checkout HEAD~1 previous commit (parent), ~2 (grand-parent)
git checkout -- reverts to last commit
git checkout HEAD filename reverts to last commit
git restore filename discard changes since last commit
git restore -- source HEAD~1 filename two commits ago
git restore -- staged filename remove added file from staging

git reset commit hash takes repo back to selected commit but file changes are left
intact useful of committed to wrong branchgit reset -- hard commit hash resets HEAD and
removes changes in working directory
git revert commit hash undo changes making a new commit to hold what was undone useful 
especially when collaborating

GIT HUB
git clone not tied particularly to git hub, can use other host services brings a clone
of a repo to local with remote already set up
remote origin is a common convention for naming a remote
git remote -v shows remote with verbose
git remote add name url 
git push -u origin branch sets upstream name of remote and pushes branch to the remote
git push if upstream was set it is used as default 

git checkout origin/main checks out the main branch from the remote
tracking branches from cloned repo
git branch -r shows branches in remote, branches do not automatically appear in list on
local
git switch branch name sets up local branch tracking instead of having detached HEAD
git fetch brings remote changes back to local without merging to local workspace
git pull updates the local HEAD same as git fetch + git merge
git pull remote branch merges changes into current branch may result in merge conflicts
git pull will default to origin and current tracking branch that is setup

GIT HUB COLLABORATORS
if private repository, by invitation collaborator can then see the repository and push
their own changes

READMEs
mark down links 
https://daringfireball.net/projects/markdown/
https://markdown-it.github.io/

GISTS
Git Hub gists are a way to share information without having to clone or fork from a full
repository. Can be made private or public.

GH PAGES
Limited to HTML/CSS/JS - free hosting through Git Hub, not intended for high traffic. 
Each repo has unlimited project pages.
Each user has one user page.
conventionally uses branch called gh-pages with index.html file along with app.CSS

COLLABORATION WORKFLOWS
centralized workflow - everyone clones the main and works on the main branch.
can result in the tip of the branch being ahead or behind. Requires pull before pushing 
Problematic because the codebase is constantly shifting/breaking

Feature Branch workflow - don't work on main "you silly goose"
Everyone clones main but creates new branches to work on. 






