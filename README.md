# Git-summery

### Book: learn version control system with git.

## What is Git

Git is a version control system.

## What is a Version Control System

- A software or utility that tracks and manages changes to a file system.
- Management of changes to documents, programs, graphics, and other files.

## Types of Version Control Systems

- VSS (Microsoft introduced it, not commonly used now)
- SVN (Apache introduced it, each user has a partial copy)
- Git (Linux introduced it, a distributed control system)

## Types of Control Systems

- Centralized Control System (working copy on central server)
- Distributed Control System (every user has a full copy)

## In Distributed Control System (DVCS)

- Commit (locally track changes, pushing syncs changes to central server)
- Clone (start by cloning the repository)
- Pull (get data from central server)
- Push (submit data to central server)

## Installation and Basic Workflow

1. Download Git and SmartGit from the website.
2. Installation (default options).

## Verifying Installation

Open the command prompt and run: `git --version`

## Installing and Setting Up Git

Open the terminal and run the following commands to set up your name and email:

- `git config --global user.name "Your Name"`
- `git config --global user.email "Your Email"`

## Checking/Set Name and Email

- `git config --global user.name`
- `git config --global user.email`

## Updating Name and Email

- `git config --global user.name "Alice"`
- `git config --global user.email "muhammadhashim555@gmail.com"`

## Installing SmartGit

1. Download from the website.
2. Installation: Mark non-commercial use only, set username and email, keep other settings default.

## Git Operations

Basic Git operations include:

- Initialize `git init`
- Add `git add`: stage files for commit (from 5 file if you want to send only 2 then we use this operation)
- Commit `git commit`: create a local snapshot
- Pull `git pull`: get data from central server
- Push `git push`: send data to central server
- Checkout `git checkout`: switch to a different branch
- Merge `git merge`: combine branches

## Advanced Operations

- Branching
- Merging
- Rebasing

## Important Terms

1. Repository: Database storing all versions of data.
2. Working Directory: Project's root folder on your local computer.
3. File Status Cycle: Untracked (add the file, it goes) -> Unmodified (edit file, it goes) -> Modified (stage the file) -> Staged -> Unmodified(commit)->unmodified
4. Staging Area: Virtual place collecting files for the next commit.

## Basic Workflow

1. Create a directory in terminal: `c:\Repo\myproject`
2. Navigate to the directory.
3. Initialize repository: `git init`
4. Create files: `first.txt` and `second.txt`
5. Check status: `git status`
6. Stage files: `git add first.txt second.txt` or `git add .`
7. Commit files: `git commit -m "Implemented new feature"`
8. View commit history: `git log`

### head

last commit wiil be head

## Commit Hash

Commit hash identifies who made a specific commit.

## Unstaging Files

- `git reset`: Remove files from the staging area.
- `git reset --hard` or "Discard" option in SmartGit: Remove files from staging area and discard changes.

## Ignoring Files

Create `.gitignore` file to exclude files from version control:

1. Ignore a specific file: `path/to/file.ext`
2. Ignore files with a certain name: `filename.ext`
3. Ignore files in a folder: `path/to/folder/*`
4. Ignore files with a certain type: `*.ext`

## Branching & Merging

- Branches manage different contexts in projects.in ervery project, there are always multiple different contexts like one for "main" and another context for each feature where work happens so the branching help us to fix bug in there own contexts
- Commands: `git branch`, `git checkout`, `git merge`

## context in projects

- In real world projects, work always happens in multipe of these contexts in parrallel
  like fixing an annoying bug (context 1)
- update some content on your FAQ pages (context 2)
- if a team member working on new feature for your shopping card (conext 3)

## application state

1. production (tested and deployed and we dont want any problem in that)
2. development ( development team working on new feature and we dont want that detaure to effect production code untile it is properly tested)
3. feature context (all feature combines in development to have final testing before deployment)

## Branch Commands

- `git branch` show the list of branch
- `git branch -v` show the list of branches with some details like last commit
- `git branch new-dev` create the new branch with name new-dev
- `git checkout new-dev` switch to "new-dev" branch
- `git log new-dev..master` show commit difference in two branch
- `git merge new-dev` Merge "new-dev" with parent branch

## short-lived and log-running branches

### short-lived

Is use to bug fix only

### log-running branches

Remain perminent you never delete it like main branch

## Demo Merge Conflict with SmartGit

Merging conflicts occur when changes conflict in the same line. if the change is in different lines then this conflicts not occur.

## Stash

Stash saves changes temporarily without committing. stash save changes tempory and it will not become a part of history.

- `git stash` save local changes
- `git stash save <name>` save local changes in stash clipboard with the name provided in the command
- `git stash list` list stashes
- `git stash pop` apply latest stash and remove from clipboard
- `git stash apply stashname` apply specific stash and stash will remain saved in clipboard

## Remote Repositories

- `git clone`: Pull code to your machine.
- `git push`: Push changes to remote repository.
- `git fetch`: Fetch changes from remote repository.
- `git pull`: Fetch and merge remote changes.

## Remote repository.

- `git pull` : fetch the changes and merge the changes from remote repository
- `git remote add repository-name(origion) https//github.... `:this command add remote repo in local repository.
- `git push -u repositoryName(origion) branchname(master)`: to connect estream or configur push destination
- `git log remote-repository-name/branch-name ` show the deatil of remote repository.
- `git remote -v`: show remote url
- `git remote show directoryname(origion) ` : show detail

standard practice is to give directory name and branch name during push.
git push "remote" "master"

## Git Workflow

when working in a team we want to review code of team member and merge code in main branch only after that. for this purpose github provide pull request.

## We should make different branching whiling working like

- production
- development
- dev-feature

## Pull requests:

when the code in dev-feature completed, the user should not merge the code directly to development. he should create pull request so the code reviewer review the code then he merge the pull request or close pull request depending on senerio.

## Forking

- Fork a repository for contributing without write access.
- Create pull requests to contribute changes back.
- The change you have made want in your repository also want into the origional repository then you are suppose to submit pull request.

## Deleting Branches

- Delete branches when no longer needed.
- `git branch -d branch-name` (local)
- `git push origin --delete branch-name` (remote)

`git branch -dr origin/branch-name` (to delete remote branch) it romve the tracked branch, but it will come back when you enter pull commant

`git push origion --delete test` : to delete the branch from remote repository as well.

`git push -f origion master` : when changed happed in remote and also in local.  
At the time of push you should first push the change. if you dont need the remote change then you use this. only git push will give error.

## Undoing Local Changes

If you have local changes that are not committed and want discard changes then you can use following commands

- `git checkout head <file/to/restore>` discard changes in a single file
- `git reset --hard HEAD` discard all uncommitted changes

## Undoing Committed Changes

- `git revert <commitHash>` undo a commit with a new commit
- `git reset --hard <commitHash>` rollback without new commits,it nether produces any new commits nor does it delete any old ones. it workis by resetting your current head branch to an old revision
- `git reset --keep <commitHash>` (preserve changes as local changes)

## Alternative to Merge: Rebase

There are two type of merge

- Fast-forward merge: this merge accur when there is changed only in one brance.
- Merge commit: when there is change in both branch then new additional commit create called merge commit.

## Rebase

`git rebase branchName`

If you dont want to make a the additonal commit or want the project's history to look as if it had evoled in a single, straight line then you should use rebase
