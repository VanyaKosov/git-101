# Script

git can be downloaded from the [official website](https://git-scm.com/downloads)

## Two types of version control

* Centralized, when repository is stored on one server. (such as Microsoft SourceSafe, SVN)
* Decentralized, when repository is stored locally, but a server can be used to sync code from multiple users. (such as Git)

## Local repository

* Git stores only differences made to files.
* Saved version of code is called a 'commit'.
* Four storages:
    * Unstaged -> Staged -> Repository -> Remote Repository

### Example

```shell
# Initialize new repository
git init

# Make new file

# Check status
git status

# Stage all changes
git add .

# Make second file

# Check status, difference between staged and unstaged
git status

# Commit staged changes
git commit -m "only staged files are committed"

# Check status, committed changes are not visible
get status

# Change committed file

# Check status
git status

# Check differences
git diff

# Stage changes
git add .

# Commit changes
git commit -m "Changed file"

# Check commits
git log
# (pay attention to commit IDs)

# Add unwanted changes

# Discard all uncommitted changes
git reset --hard

# Check status, no changes
git status

# See what changed in any commit (using commit id found in 'git log')
git show <commit_id>
```

## Single + remote repository
