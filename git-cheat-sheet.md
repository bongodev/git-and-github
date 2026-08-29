git Daily Commands Cheatsheet

A quick-reference guide for the most common Git commands used in a daily development workflow.

---

## 🔁 The Standard Daily Workflow
Use these commands continuously to track and save your progress.

* `git status`
  * **What it does:** Shows modified, staged, or untracked files.
  * *Tip: Run this before and after major steps to see exactly what Git is tracking.*
* `git add .`
  * **What it does:** Stages all current changes (new, modified, and deleted files) for the next commit.
* `git add <file-name>`
  * **What it does:** Stages a single specific file, leaving other modified files untouched.
* `git commit -m "your descriptive message"`
  * **What it does:** Saves your staged snapshot into your local repository history.

---

## 🔀 Branching & Feature Management
Always create a separate branch when starting a new task or fixing a bug.

* `git branch`
  * **What it does:** Lists your local branches. Your current active branch is marked with an asterisk `*`.
* `git switch -c <new-branch-name>`
  * **What it does:** Creates a brand new branch and switches to it immediately.
* `git switch <branch-name>`
  * **What it does:** Moves from your current branch to an existing one.
* `git merge <branch-name>`
  * **What it does:** Combines the code from the specified branch into your current active branch.

---

## 🌐 Syncing with Remote Repositories (GitHub/GitLab)
Keep your local machine updated with your team's code and share your work.

* `git pull`
  * **What it does:** Downloads updates from the remote server and merges them directly into your current branch.
* `git pull --rebase`
  * **What it does:** Fetches changes but places your local commits cleanly on top of the remote changes, avoiding merge commits.
* `git push`
  * **What it does:** Uploads your local commits to the remote server.
* `git push -u origin <branch-name>`
  * **What it does:** Links a brand-new local branch to the remote repository and uploads it for the first time.
* `git fetch`
  * **What it does:** Downloads remote history updates so you can see what your team did without changing your local files yet.

---

## 🔍 Inspecting Changes & History
Review your changes before sharing them with your team.

* `git diff`
  * **What it does:** Shows line-by-line changes made in your code that are not yet staged.
* `git diff --staged`
  * **What it does:** Shows changes that are staged and ready to be committed.
* `git log --oneline --graph`
  * **What it does:** Displays a clean, visual timeline of past commits.

---

## 🛠️ Handling Interruptions & Mistakes
Fix minor typos or quickly swap tasks without losing code.

* `git stash`
  * **What it does:** Cleans your working directory by saving uncommitted work to a hidden, temporary shelf.
* `git stash pop`
  * **What it does:** Restores your latest stashed files so you can resume work.
* `git commit --amend -m "updated message"`
  * **What it does:** Overwrites your very last commit with a new message or newly staged files.
* `git restore <file-name>`
  * **What it does:** Destroys local, unstaged edits and resets the file back to its last committed state.

