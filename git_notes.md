# Week 3 (self study) 9-15 May 2016
----------------------------------


[source](https://www.atlassian.com/git/tutorials/setting-up-a-repository/git-config)

- directory vs repository?? - directory: local, repo: remote

```
git init
git init <directory> #directory=myproject.git
git init --bare <directory> #create central storage repository for the project
```

- cloning creates a remote connection called origin pointing back to the original repository.

```
git clone <repo> # create local copies
git clone <repo> <directory> # clone <repo> to the local <directory>

git add # add changes in directory to staging area
git add <file>
git add <directory>
```

- summarize the entire commit on the first line in less than 50 characters, leave a blank line, then a detailed explanation of what’s been changed

```
git commit # commit staged snapshot to project history
git commit -m "<message>"
git commit -a # commit all staged changes
```

```
git status
git remote # bookmarks to other repositories
git remote -v # view URLs as well
git remote add <name> <url>
git remote rm <name>
git remote rename <old-name> <new-name>
ssh://user@host/path/to/repo.git

git fetch <remote> # import commits from remote repo, do not integrate to local, store as a remote branch, can review
git fetch <remote> <branch> # only fetch a specific branch

git branch # view branches
git branch -r # view remote branches
git checkout <branch> # switch to <branch>
git push <remote> <branch> # push branch to remote (only push to bare repos)
git pull -- rebase <remote>
```



example:
```
git checkout master
git fetch origin master
git rebase -i origin/master
# Squash commits, fix up commit messages etc.
git push origin master
```
