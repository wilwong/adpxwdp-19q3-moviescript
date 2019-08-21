# Git Cheatsheet

## Things to remember

* git doesn't save a file, it saves the diff of a file
* your machine is the local, the git server is the remote, even though that server is the centralized management
* your machine has no remote name, the main git server (probably github or gilab) is probably named origin
* dont be afraid of conflicts
* some guys will have commitment issues and they cant push, and that's okay
* Software recommended to view the git train track
  * [Git Fork](https://git-fork.com)
  * [Sublime Merge](https://www.sublimemerge.com/)

### Git Terminologies

coming soon...

## Common Commands

### Set up

```bash
# initilize a git
git init

# add your remote 
git remote add origin [GIT URL]

# view all your remotes
git remote -v
```

### Saving Progress

***REMEMBER :*** git is a *3 STAGE* save process

```bash
# add a particular file
git add [FILE NAMES]

# add all the files
git add .

# check which file is modified and added and which is not
git status

# commit the files to your local git
git commit -m "meaningful explanation of your commit"

# -m means commit with a message, if you forgot to use option -m
# git will make you type a message in vim. In that case :-
#   1. type `i` to get into insert mode,
#   2. type your msg
#   3. hit esc to get out from insert mode
#   4. type `:` followed by `x` to command a save-and-exit 

# push the local commitments to the server (most probably github)
git push

# when you push to a new repo, you will be asked to explicitly set up the upstream branch
git push --set-upstream-to [REMOTE NAME] [BRANCH NAME]
```

### Retreving Progress

```bash
# To get the lastest progress info from git
git fetch

# And then you merge them to your local copy
git merge


# It more common to use the 2-in-1 quickhand called `git pull`, 
# It literally runs `git fetch` followed by `git merge` for you
git pull

# To get a specific file from last commit
git checkout [FILE NAME]

```

### Branching
```bash
# To make a new branch
git branch [NEW BRANCH NAME]

# To get on that branch
git checkout [NEW BRANCH NAME]

# The 2-in-1 quickhand
git checkout -b [NEW BRANCH NAME]

# show all the branchs
git branch -a 
```

###  Merge back to Master
***REMEMBER :*** always do a 2-step merge
```bash
# Fetch all the info from the servers first
git fetch 

# You can also just use pull instead of fetch
git pull

# if there are changes in the master, you will have to explicitly merge
git checkout master
git merge

# You can also just pull instead of merge
git checkout master
git pull

# Now that you are up-to-date on master, go back to your branch
git checkout [YOUR BRANCH]
git merge master

# This is the part you may have to resolve conflicts
# after you resolved all conflicts, commit the resolve
git add .
git commit -m "resolved conflicts like a boss"
git push

# Now you are finally ready to merge into master
# But, pull again just incase
git checkout master
git pull 

# If there's no new commits from master, back merge
git merge [YOUR BRANCH]

# Push that merge
git push

```

### Settling Conflicts

coming soon...

## More Advanced Ops

coming soon...