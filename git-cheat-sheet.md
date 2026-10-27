# Adding a git-cheat-sheet for practice 


Git Cheat SheetA practical quick-reference guide for daily Git commands, workflows, and troubleshooting.1. Initial Setup & ConfigurationConfigure user info, default branch, and global editor.# Set your name and email globally
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Set default branch name to 'main'
git config --global init.defaultBranch main

# Set default code editor (e.g., VS Code)
git config --global core.editor "code --wait"

# Enable colorful output
git config --global color.ui auto

# List all current configurations
git config --list --show-origin
2. Starting a Repository# Initialize a new Git repository in the current directory
git init

# Clone an existing remote repository
git clone <remote-url>

# Clone a specific branch only
git clone -b <branch-name> --single-branch <remote-url>
3. Basic Snapshotting & Staging# Check status of working directory and staged files
git status

# Check status in compact format
git status -s

# Stage a specific file
git add <file>

# Stage all modified and new files
git add .

# Unstage a file while keeping file changes in working directory
git restore --staged <file>

# Commit staged changes with an inline message
git commit -m "Commit title: concise description"

# Stage all tracked modified files and commit in one step
git commit -am "Commit message"

# Amend the most recent commit (change message or add newly staged files)
git commit --amend -m "Updated commit message"
4. Branching & Merging# List local branches (* indicates currently checked-out branch)
git branch

# List both local and remote tracking branches
git branch -a

# Create a new branch
git branch <branch-name>

# Switch to a branch
git switch <branch-name>
# (legacy alternative)
git checkout <branch-name>

# Create and immediately switch to a new branch
git switch -c <new-branch>
# (legacy alternative)
git checkout -b <new-branch>

# Merge a branch into your current active branch
git merge <branch-name>

# Delete a local branch (safe delete; fails if unmerged)
git branch -d <branch-name>

# Force-delete a local branch
git branch -D <branch-name>

# Delete a remote branch
git push origin --delete <branch-name>
5. Inspecting History & Changes# View full commit history
git log

# View compact, one-line-per-commit history with graphical branch tree
git log --oneline --graph --decorate --all

# View commits affecting a specific file
git log -p <file>

# View working tree changes that are NOT staged yet
git diff

# View staged changes (ready to commit) vs last commit
git diff --staged

# View differences between two branches
git diff <branch-a>..<branch-b>

# Show who changed each line in a file and in which commit
git blame <file>

# Show metadata and content changes for a specific commit
git show <commit-hash>
6. Remote Repositories# List all configured remotes with URLs
git remote -v

# Add a new remote connection
git remote add origin <remote-url>

# Fetch latest references and objects from remote without merging
git fetch origin

# Fetch and merge changes from the remote tracking branch into current branch
git pull origin <branch-name>

# Fetch and rebase (cleaner commit history)
git pull --rebase origin <branch-name>

# Push local commits to remote and set tracking upstream
git push -u origin <branch-name>

# Push changes on current branch to configured upstream
git push
7. Stashing (Temporary Storage)Save uncommitted changes without making a commit to switch context cleanly.# Stash current modified tracked files
git stash

# Stash including untracked files with a custom message
git stash push -u -m "WIP: feature login form"

# List all saved stashes
git stash list

# Re-apply the most recent stash and remove it from stash list
git stash pop

# Re-apply the most recent stash without removing it
git stash apply

# Apply a specific stash from the list
git stash apply stash@{1}

# Drop a specific stash
git stash drop stash@{0}

# Clear all stashes
git stash clear
8. Undoing Changes & RecoveryAction / ProblemCommandNoteDiscard uncommitted changes in a specific filegit restore <file>Overwrites working directory changes permanentlyUnstage a file without losing editsgit restore --staged <file>Keeps file contents intactRevert an existing commit safely (adds a new inverse commit)git revert <commit-hash>Safe for shared / public branchesSoft reset (move HEAD back, keep changes staged)git reset --soft HEAD~1Great for re-grouping commitsMixed reset (default: uncommit & unstage changes)git reset HEAD~1Keeps changes in working directoryHard reset (discard commit AND all local changes)git reset --hard HEAD~1Destructive: destroys uncommitted workRecover lost commits or deleted branchesgit reflog then git checkout <hash>Reflog tracks every movement of HEAD9. Rebasing & Advanced Workflows# Rebase current branch onto main (linear history)
git rebase main

# Abort an in-progress rebase after conflicts
git rebase --abort

# Continue rebase after resolving conflict markers and staging
git rebase --continue

# Interactive rebase (squash, reword, drop last N commits)
git rebase -i HEAD~3

# Cherry-pick a specific commit into the current branch
git cherry-pick <commit-hash>

# Clean untracked files (dry-run first to preview)
git clean -dn

# Actually delete untracked files
git clean -df
10. Useful Git AliasesAdd these shortcuts to your ~/.gitconfig for faster terminal navigation:git config --global alias.st "status -s"
git config --global alias.co "checkout"
git config --global alias.sw "switch"
git config --global alias.br "branch"
git config --global alias.ci "commit"
git config --global alias.lg "log --oneline --graph --decorate --all"
git config --global alias.unstage "restore --staged"

