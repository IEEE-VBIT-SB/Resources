# Basic Commands

## Git Config

`git config -- global user.name NAME` = set user name globally
`git config --global user.email EMAIL` = set user email globally
`git config user.name || git config user.email` = check saved info

# Creating repo

`git init` = creates a git repository in the directory currently in

# Staging

`git status` = to check status , if staged or unstaged
`git add FILE_NAME` = to add a file to staging area
`git rm --cached FILE_NAME` = to remove a file from staging area
`git add .` = to add all files in project to staging area

# Commiting

`git commit -m "Specific Changes Made"` = commits the staging area giving them a specific id

`git log` = shows all the commits with details

`git log --oneline` = shows all the commits in one line each

## Git Stash

`git stash` = clears the changes to the initial state (last commit) & creates a unique id for the current state
`git stash apply` = brings back the current state using git stash multiple times creates a list of stashes of all states with multiple ids
`git stash list` = shows all the stash (States) with their ID
`git stash apply ID` = ID will be the number , which state you want to go back to
`git stash push -m "Your message"` = used to give description to stash
`git stash drop ID` = used to remove a stash saved
`git stash pop ID` = applies the specific stash and removes it from history
`git stash clear` = removes all the stash history

# Gitignore

a `.gitignore` file can be created , in which you can specify all the folders/files that should not be staged and commited
For example : `node_modules/ .css.map` etc.
It's Good to create a gitignore at the start of Project

# Reverting & Reset

- use `git log --oneline` to see the commit_ID to change to
- Checkout commit :
- - `git checkout commit_ID` = to just check the commit id entered , see it in read only ... changes will not be saved
- - `git checkout master` = to come back to original commit (As checkout removes us from master branch)
- Revert commit :

- - `git revert commit_ID` = to remove the changes of the provided commit (will add a new revert commit and remove the changes of the specific commit)

# Github

- Creating new & Cloning Repo
- - create a new repo on Github and copy the URL
- - now push your code to it with
- - `git push git_url master` = pushing code of master branch (to push all branches replace master with --all)
- - creating an alias to not always type URL
- - `git remote add origin git_url` = origin can be name of anything else, but origin is the word most commonly used
- - `git push origin master` = to push code to using alias
- - `git push -u origin master` = pushes and starts tracking the branch (u don't need to specify it again , ex. if pulling)
- - `git clone git_url` = will copy the repo to current directory and also add the origin alias by default
- - `git remote -v` = to check all the aliases made
- - adding id and password in push\pull :
- - - replacing the origin in `git push origin master`
- - - `git push https://username:password@repo_url.git master`
- - - if password contains @ replace it with %40
- - - NOTE : this can store your password in plain text
- - - to avoid this you can remove the password and enter it later
- - `git push https://username@repo_url.git master`
- Collaborating
- - Most of the collaboration features are already available on Github, Example
- - `git pull git_url` = to pull changes from remote to local repo
- - create a branch and make your changes
- - `git push origin branch_name` = to push the specific branch to remote
- - create a Compare & Pull Request when you want are ready for the branch to be merged (with a message)
    the reviewer of the repo will accept the changes and merge it (and specify a merge commit message)
- - pull the project every time before editing to see the changes
- - `git branch -r` = helps us to see the remote branches & the connections
- Forking (Contributing)
- - to contribute to an open source project
- - click on fork , which will copy the repo to your account
- - make changes by pulling the repo, then push it ( this will happen on your account )
- - then go to the owner account's repo and create a pull request there
- - the owner can compare the changes and accept your changes
- - which will end up merging your changes to their project
