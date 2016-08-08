# ProGit book

## config settings

stored in:
1. `/etc/gitconfig` with `--system` optionr -- this is system-wide
2. `~/.gitconfig` or `~/config/git/config` with the `--global` option -- this is user-specific
3. `.git/config` specific for that repo

set values:
- `git config --global user.name "John Doe"`
- `git config --global user.email abc@abc.abc`
- `git config --global core.editor vim`

to check settings:
- `git config --list`
- `git config user.name`

## help
- `git help <verb>`
- `git <verb> --help`
- `man git-<verb>`


## diff

`git diff`, `git diff --staged` or `git diff --cached`  
`git difftool` instead of `diff` to use an external tool.  
`git difftool --tool-help` to view what is available (emerge, vimdiff, etc.)  


## remove, move (rename)
`git rm <filename>` removes the file from working directory and staging area (even if file has already been removed from working directory with `rm`)  
`git rm <filename> -f` need to force if the file to be deleted has already been modified and staged  
`git rm --cached <filename>` to untrack (remove from index) but keep in the working directory (can be added to `.gitignore` then)  
`git rm <arg>` where `<arg>` can be files, directories and file-glob patterns, e.g. `git rm log/\*.log`  to remove all `.log` files from the `log/` directory  

`git mv <old_name> <new_name>` which is equivalent to: `mv <old_name> <new_name>` then `git rm <old_name>` then `git add <new_name>`  


## commit
`git commit` to open an editor with the status message  
`git commit -v` to open an editor with the status message and diff info (these will not be included in the message)  
`git commit -a` stage all tracked files and commit (`git commit -a -m 'xy'`)  


## log
`git log -p -2` where `-2` limits to the 2 last commits and `-p` prints the diffs between commits  
`git log --stat` to view abbreviated stats for each commit  
`git log --pretty=oneline` or `git log --pretty=short` or `git log --pretty=full` or `git log --pretty=fuller`  
`git log --pretty=format: "%h %s"` to print custom format (e. g. abbreviated hash and subject)  
`git log --pretty=format: "%h %s" --graph` to print an ASCII graph as well  

`git log -S<string>` to filter commits where the change included the `<string>`





# Week 3 (self instructed) 9-15 May 2016
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
