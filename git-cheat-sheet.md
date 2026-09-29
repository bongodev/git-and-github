# THIS LINE HAS BEEN ADDED FOR TESTING.
# -----------------------------
# GIT BASIC CHEAT SHEET
# -----------------------------

# Check Git version
git --version


# -----------------------------
# CONFIGURATION
# -----------------------------

# Set username
git config --global user.name "Your Name"

# Set email
git config --global user.email "your@email.com"

# Show Git configuration
git config --global --list

# Make "main" the default branch for new repositories
git config --global init.defaultBranch main


# -----------------------------
# START A REPOSITORY
# -----------------------------

# Initialize Git in current folder
git init

# Initialize Git with main as first branch
git init -b main

# Clone a repository
git clone git@github.com:USERNAME/REPOSITORY.git


# -----------------------------
# CHECK STATUS
# -----------------------------

# Show current status
git status

# Show current branch
git branch

# Show all local and remote branches
git branch -a


# -----------------------------
# ADD / STAGE FILES
# -----------------------------

# Add one file
git add filename

# Add all files
git add .

# Add all changes including deleted files
git add -A


# -----------------------------
# COMMIT
# -----------------------------

# Create commit
git commit -m "Commit message"

# Add tracked files and commit
git commit -am "Commit message"


# -----------------------------
# HISTORY
# -----------------------------

# Show commit history
git log

# Compact commit history
git log --oneline

# Show history with branches
git log --oneline --graph --all

# Show commits plus exact changes
git log -p


# -----------------------------
# DIFF
# -----------------------------

# Show unstaged changes
git diff

# Show staged changes
git diff --staged


# -----------------------------
# BRANCHES
# -----------------------------

# Create new branch
git branch branch-name

# Switch branch
git switch branch-name

# Create and switch to new branch
git switch -c branch-name

# Older command for switching branches
git checkout branch-name

# Create and switch using checkout
git checkout -b branch-name

# Rename current branch to main
git branch -m main

# Delete local branch
git branch -d branch-name

# Force delete local branch
git branch -D branch-name


# -----------------------------
# MERGE
# -----------------------------

# Switch to target branch first
git switch main

# Merge another branch into current branch
git merge branch-name


# -----------------------------
# REMOTES
# -----------------------------

# Show remote names
git remote

# Show remote names and URLs
git remote -v

# Add remote
git remote add origin git@github.com:USERNAME/REPOSITORY.git

# Add remote with custom name
git remote add murad git@github.com:USERNAME/REPOSITORY.git

# Show remote URL
git remote get-url origin

# Change remote URL
git remote set-url origin git@github.com:USERNAME/NEW-REPOSITORY.git

# Remove remote
git remote remove remote-name


# -----------------------------
# PUSH
# -----------------------------

# Push branch and set upstream
git push -u origin main

# Push current branch after upstream is set
git push

# Push a specific branch
git push origin branch-name

# Force push
git push --force

# Delete remote branch
git push origin --delete branch-name


# -----------------------------
# FETCH / PULL
# -----------------------------

# Download remote information only
git fetch

# Download from all remotes
git fetch --all

# Download + merge remote changes
git pull

# Pull from specific remote and branch
git pull origin main


# -----------------------------
# UNDO CHANGES
# -----------------------------

# Discard changes in one file
git restore filename

# Discard all unstaged changes
git restore .

# Unstage one file
git restore --staged filename

# Unstage everything
git restore --staged .


# -----------------------------
# RESET
# -----------------------------

# Move HEAD back but keep changes staged
git reset --soft HEAD~1

# Move HEAD back and keep changes unstaged
git reset HEAD~1

# Completely delete last commit and changes
git reset --hard HEAD~1


# -----------------------------
# STASH
# -----------------------------

# Temporarily save changes
git stash

# Show stashes
git stash list

# Restore latest stash
git stash pop

# Restore stash without deleting it
git stash apply


# -----------------------------
# TAGS
# -----------------------------

# Show tags
git tag

# Create tag
git tag v1.0

# Push tags
git push origin --tags


# -----------------------------
# REMOVE FILES
# -----------------------------

# Remove tracked file
git rm filename

# Remove tracked directory
git rm -r directory-name


# -----------------------------
# USEFUL SHORT COMMANDS
# -----------------------------

# Current status
git status

# Current branch
git branch

# Remote details
git remote -v

# Short history
git log --oneline

# Graph history
git log --oneline --graph --all

# Last commit
git show

# Show files in last commit
git show --stat
