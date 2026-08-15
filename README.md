# Git & GitHub Learning Notes 🚀

This repository contains my personal learning notes and practice while learning **Git and GitHub** from a complete Git & GitHub tutorial.

I created this repository to document what I learned, practice Git commands, and build a better understanding of how version control and GitHub collaboration work in real-world development.

---

## 🎥 Learning Resource

I learned these concepts from the following Git & GitHub course:

**▶️ [Watch the Git & GitHub Course]([https://www.youtube.com/watch?v=VIDEO_ID](https://youtu.be/roA-RnZa7Og?si=hhzmewmwNk-bXXol))**

---

## 📚 What I Learned

## 1. Git vs GitHub

I learned the difference between **Git** and **GitHub**.

* **Git** is a distributed version control system.
* **GitHub** is a cloud-based platform for hosting Git repositories.
* Git helps me track changes in my code.
* GitHub helps me store, share, and collaborate on projects.
* Version control helps prevent losing code and makes collaboration easier.

---

# 2. Git Architecture

I learned the basic architecture of Git and how changes move through different stages.

```text
Working Directory
       ↓
Staging Area
       ↓
Local Repository
       ↓
Remote Repository (GitHub)
```

### Working Directory

This is where I create and modify my project files.

### Staging Area

The staging area contains the changes that I want to include in my next commit.

### Local Repository

The local repository stores my commits and project history.

### Remote Repository

The remote repository, such as GitHub, stores my project online and allows me to collaborate with others.

---

# 3. Git Setup

Before using Git, I learned how to check the installation and configure my Git identity.

### Check Git Version

```bash
git --version
```

**What it does:**
Shows the installed Git version.

### Configure Username

```bash
git config --global user.name "Your Name"
```

**What it does:**
Sets the username that Git will associate with my commits.

### Configure Email

```bash
git config --global user.email "your-email@example.com"
```

**What it does:**
Sets the email address associated with my Git commits.

### Check Configuration

```bash
git config --list
```

**What it does:**
Shows my current Git configuration.

---

# 4. Creating a Git Repository

I learned how to create a new Git repository for a project.

### Initialize Git

```bash
git init
```

**What it does:**
Creates a new `.git` directory and turns my project into a Git repository.

### Check Repository Status

```bash
git status
```

**What it does:**
Shows modified, untracked, and staged files.

### Clone an Existing Repository

```bash
git clone https://github.com/username/repository.git
```

**What it does:**
Downloads an existing GitHub repository to my local computer.

---

# 5. Working Directory & Staging Area

I learned how to move changes from the working directory to the staging area.

### Check Changes

```bash
git status
```

**What it does:**
Shows which files have been modified, added, deleted, or staged.

### Add One File

```bash
git add filename.js
```

**What it does:**
Adds a specific file to the staging area.

### Add Multiple Files

```bash
git add file1.js file2.js
```

**What it does:**
Adds multiple specific files to the staging area.

### Add All Changes

```bash
git add .
```

**What it does:**
Adds all changes in the current directory to the staging area.

### Remove a File from Staging

```bash
git reset filename.js
```

**What it does:**
Removes the file from the staging area without deleting the file.

---

# 6. Commit

I learned that a **commit** creates a snapshot of my staged changes in the local repository.

### Create a Commit

```bash
git commit -m "Add initial project files"
```

**What it does:**
Saves the staged changes with a descriptive message.

### View Commit History

```bash
git log
```

**What it does:**
Shows the complete commit history.

### Short Commit History

```bash
git log --oneline
```

**What it does:**
Shows a shorter version of the commit history.

### Check the Latest Commit

```bash
git show
```

**What it does:**
Shows information about the latest commit and its changes.

---

# 7. Reset & Undo Changes

I learned how to undo or reset changes when necessary.

### Unstage a File

```bash
git reset filename.js
```

**What it does:**
Removes the file from staging but keeps the changes in the working directory.

### Unstage Everything

```bash
git reset
```

**What it does:**
Removes all staged files from the staging area.

### Soft Reset

```bash
git reset --soft HEAD~1
```

**What it does:**
Removes the latest commit but keeps the changes staged.

### Mixed Reset

```bash
git reset --mixed HEAD~1
```

**What it does:**
Removes the latest commit and unstages the changes while keeping the files modified.

### Hard Reset

```bash
git reset --hard HEAD~1
```

**What it does:**
Removes the latest commit and discards the changes.

> ⚠️ **Important:** `git reset --hard` can permanently remove uncommitted changes, so I should use it carefully.

---

# 8. Branching

I learned how branches allow me to work on different features without directly modifying the `main` branch.

### Show Branches

```bash
git branch
```

**What it does:**
Shows all local branches.

### Create a Branch

```bash
git branch feature
```

**What it does:**
Creates a new branch named `feature`.

### Switch Branch

```bash
git checkout feature
```

**What it does:**
Switches to the `feature` branch.

### Create and Switch to a New Branch

```bash
git checkout -b feature
```

**What it does:**
Creates a new branch and immediately switches to it.

### Modern Alternative

```bash
git switch -c feature
```

**What it does:**
Creates and switches to a new branch.

### Delete a Branch

```bash
git branch -d feature
```

**What it does:**
Deletes the local `feature` branch.

---

# 9. Merging

I learned how to combine changes from one branch into another.

For example, after completing a feature:

```bash
git checkout main
git merge feature
```

**What it does:**

1. Switches to the `main` branch.
2. Merges the changes from the `feature` branch into `main`.

### Example Workflow

```bash
git checkout -b feature

# Make changes to the project

git add .
git commit -m "Add new feature"

git checkout main
git merge feature
```

---

# 10. Merge Conflicts

I learned that merge conflicts can happen when two branches modify the same part of a file.

The general workflow is:

```text
Create Branch
     ↓
Make Changes
     ↓
Commit Changes
     ↓
Switch to Main
     ↓
Merge Branch
     ↓
Conflict?
   ↙     ↘
 Yes      No
 ↓         ↓
Resolve   Done
Conflict
 ↓
Add Changes
 ↓
Commit
```

When a conflict happens, Git adds conflict markers to the file:

```text
<<<<<<< HEAD
Changes from main
=======
Changes from feature
>>>>>>> feature
```

I need to manually decide which code should remain.

After resolving the conflict:

```bash
git status
git add .
git commit -m "Resolve merge conflict"
```

---

# 11. GitHub & Remote Repository

I learned how to connect my local repository with a GitHub repository.

### Add GitHub Remote

```bash
git remote add origin https://github.com/username/repository.git
```

**What it does:**
Connects my local repository to the GitHub repository.

### Check Remote

```bash
git remote -v
```

**What it does:**
Shows the remote repository URLs.

### Rename Remote

```bash
git remote rename origin upstream
```

**What it does:**
Renames a remote repository.

### Remove Remote

```bash
git remote remove origin
```

**What it does:**
Removes the remote connection from my local repository.

---

# 12. Push

I learned how to upload my local commits to GitHub.

### First Push

```bash
git push -u origin main
```

**What it does:**
Uploads the `main` branch to GitHub and sets the upstream branch.

### Normal Push

```bash
git push
```

**What it does:**
Uploads my new commits to the connected remote branch.

### Push a Specific Branch

```bash
git push origin feature
```

**What it does:**
Uploads the `feature` branch to GitHub.

---

# 13. Fetch

I learned that `git fetch` downloads information about changes from the remote repository without automatically merging those changes into my current branch.

```bash
git fetch origin
```

**What it does:**
Downloads the latest remote changes and updates my remote-tracking branches.

### Fetch All Remotes

```bash
git fetch --all
```

**What it does:**
Fetches changes from all configured remotes.

---

# 14. Pull

I learned that `git pull` downloads changes from the remote repository and integrates them into my current branch.

```bash
git pull origin main
```

**What it does:**
Gets the latest changes from the `main` branch on GitHub and integrates them into my local `main` branch.

### Fetch vs Pull

```text
git fetch
    ↓
Download remote changes
    ↓
Review changes
    ↓
No automatic merge
```

```text
git pull
    ↓
Download remote changes
    ↓
Integrate changes
```

---

# 15. Useful Git Commands

### See the Current Status

```bash
git status
```

### See Commit History

```bash
git log
```

### See Short Commit History

```bash
git log --oneline
```

### See All Branches

```bash
git branch -a
```

### See Remote Information

```bash
git remote -v
```

### See Changes Before Staging

```bash
git diff
```

### See Staged Changes

```bash
git diff --staged
```

---

# 🔥 My Complete Git Workflow

This is the basic workflow I learned and can use in my projects:

```bash
# 1. Initialize Git
git init

# 2. Check status
git status

# 3. Add files
git add .

# 4. Create commit
git commit -m "Initial commit"

# 5. Create feature branch
git checkout -b feature

# 6. Make changes
# ...

# 7. Check changes
git status

# 8. Stage changes
git add .

# 9. Commit changes
git commit -m "Add new feature"

# 10. Switch to main
git checkout main

# 11. Merge feature
git merge feature

# 12. Add GitHub remote
git remote add origin https://github.com/username/repository.git

# 13. Push to GitHub
git push -u origin main
```

---

# 🔄 Daily Git Workflow

When working on an existing project, my typical workflow can be:

```bash
# Get the latest changes
git pull

# Check current status
git status

# Create a feature branch
git checkout -b feature-name

# Work on the project
# ...

# Check changes
git status

# Review changes
git diff

# Stage changes
git add .

# Commit changes
git commit -m "Add feature"

# Push feature branch
git push -u origin feature-name
```

---

# 🧠 My Learning Summary

From this course, I learned the fundamentals of **Git and GitHub**, including:

* Git and GitHub
* Version control
* Git architecture
* Working directory
* Staging area
* Local repository
* Remote repository
* Git initialization
* Git cloning
* Git status
* Git add
* Git commit
* Git reset
* Git diff
* Git log
* Git branches
* Branch switching
* Git merging
* Merge conflicts
* GitHub remote repositories
* Git push
* Git fetch
* Git pull

Most importantly, I learned how these commands work together as part of a real development workflow.

---

# 🛠️ Commands I Practiced

```bash
# Git Setup
git --version
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --list

# Repository
git init
git clone <repository-url>
git status

# Staging
git add .
git add <file>
git reset <file>

# Commit
git commit -m "Commit message"
git log
git log --oneline
git show

# Undo / Reset
git reset
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1

# Branch
git branch
git branch <branch-name>
git checkout <branch-name>
git checkout -b <branch-name>
git switch <branch-name>
git switch -c <branch-name>
git branch -d <branch-name>

# Merge
git merge <branch-name>

# Remote
git remote -v
git remote add origin <repository-url>
git remote rename origin <new-name>
git remote remove origin

# GitHub
git push
git push origin main
git push -u origin main
git fetch
git fetch origin
git fetch --all
git pull
git pull origin main

# Compare Changes
git diff
git diff --staged
```

---

# 🎯 What I Want to Improve Next

After learning the basics, I want to improve my practical Git and GitHub skills by:

* Practicing Git with my real projects
* Using meaningful commit messages
* Working with multiple branches
* Practicing merge conflict resolution
* Learning GitHub Pull Requests
* Learning Code Review
* Learning GitHub Issues
* Learning GitHub Actions
* Improving my team collaboration workflow

---

## 📌 Final Note

This repository is part of my **learning journey as a developer**.

I created these notes so I can come back later and quickly review Git and GitHub concepts whenever I need them.

> **Learn → Practice → Build → Commit → Push → Improve 🚀**

---

## 📖 References

* [Git Documentation](https://git-scm.com/docs)
* [GitHub Documentation](https://docs.github.com/)
* [Git Official Website](https://git-scm.com/)

---

### ⭐ Keep Learning & Keep Building!

I am continuously improving my development skills by learning new technologies and applying them to real-world projects.
