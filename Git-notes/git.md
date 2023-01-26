# Git Notes
## Basic Workflow

1. Clone repository onto local machine.
```
git clone <repo> <local-repo-name>
```

2. Stage changes. Stage all changes by using `<directory>` or a single file with `<file>`.
```
git add <dir/file>
```
3. Commit changes with a short message.
```
git commit -m "<message>"
```
4. Pull any remote changes. Push local commits to remote branch. 
```
git pull <remote>
```
```
git push <remote> <branch>
```

## Branching
| Command | Description |
|--------|-------------|
| `git branch` | List all of the branches in your repo. Add a \<branch> argument to create a new branch with the name \<branch>.|
| `git checkout -b <branch>` | Create and check out a new branch named <branch>. Drop the -b flag to checkout an existing branch.|  
 `git merge <branch>` | Merge <branch> into the current branch Leave off <branch> to fetch all remote refs.|
|`git fetch <remote> <branch>`|Fetches a specific <branch>, from the repo.|

## Troubleshooting
| Command | Description |
|--------|-------------|
| `git status` | List which files are staged, unstaged, and untracked.|
| `git log` | Display the entire commit history using the default format. For customization see additional options.|  
 `git diff` | Show unstaged changes between your index and working directory.|
|`git config --global user.name <name>`|Define the author name to be used for all commits by the current user.|
|`git reset <file>`|Remove <file> from the staging area, but leave the working directory unchanged. This unstages a file without overwriting any changes.|