# Script

git can be downloaded from the [official website](https://git-scm.com/downloads)

## Two types of version control

* Centralized, when repository is stored on one server. (such as Microsoft SourceSafe, SVN)
* Decentralized, when repository is stored locally, but a server can be used to sync code from multiple users. (such as Git)

## Local repository

* Git stores only differences made to files.
* Saved version of code is called a `commit`.
* Four storages:
    * `Unstaged` -> `Staged` -> `Repository` -> `Remote Repository`

### Example

* When making commit commit for the first time, you will be asked your e-mail and name, which will be included in each commit.
* `.gitignore` file can be used to exclude some files from being committed. Possible uses include:
  * Secret files such as passwords or tokens
  * Compiled binary files (`*.jar`, `*.class`)

```shell
# Initialize new repository
git init
# Repository created repository is stored in `.git` folder

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

# See what changed in any commit (using commit id found in `git log`)
git show <commit_id>
```

## Single + remote repository

* There are many services that provide remote repository functionality (such as: GitHub, GitLab, BitBucket, self-hosted).
* Benefits of remote repository include: 
  * Backup (private/public)
  * Synchronization between multiple devices
  * Shared development
* Accessing a remote repository requires authentication, such as:
  * SSH (Secure Shell) key (no login or password required)
    * Should generate unique key for every device.
    * Consists of public and private key pair.
    * Public key can be given to anyone.
    * Private key should not be shared with anyone.
  * HTTP (requires login and password)

### Example

First, you need to create an account on one of the git hosted services.
(For testing purposes, self-hosted service is running [here](http://localhost))

```shell
# Generate SSH key (public and private pair), generated files are found at ~/.ssh
# Already generated for this computer
ssh-keygen -t ed25519 -C "SSH key name"

# Find public SSH key
cat ~/.ssh/id_ed25519.pub

# Add public key to your account

# Create a new repository on the website (also change default branch to master)

# Change origin URL to SSH

# Connect local repository to the remote one
git remote add origin git@localhost:Admin/GitPresentation.git

# Upload the repository to the server
git push -u origin 



# Switch to HTTP (could have been done initially)
# On the website: Click `CODE`, then select `HTTP`, and copy URL
# In the console: switch origin from SSH to HTTP
git remote set-url origin http://localhost/Admin/GitPresentation.git

# Make some changes, stage, commit

# Push to the server
git push

# Switch back to SSH (for convenience)
git remote set-url origin git@localhost:Admin/GitPresentation.git

# Switch to another folder

# Clone existing repository (need to be cloned only for the first time)
git clone git@localhost:Admin/GitPresentation.git

# Make changes in one of the folders
# Stage, commit, push

# In the other folder, retrieve the changes
git pull
```

## Multiple contributors

