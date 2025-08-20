# 🌱 Beginner’s Guide to Git & GitHub (With Branching)

This guide takes you from **zero knowledge of Git** to working with **GitHub branches, pull requests, and collaboration**.  
Everything is explained in a proper flow with commands and definitions.

---

## 1. 🔹 What is Git?
Git is a **version control system (VCS)** that tracks changes in your code.  
It allows you to:
- Save different versions of a project.
- Work on code with teammates.
- Revert back if something breaks.

👉 Think of it as a **time machine + collaboration tool** for your code.

---

## 2. 🔹 What is GitHub?
GitHub is a **cloud platform** that hosts your Git repositories online.  
It lets you:
- Store repositories on the internet.
- Collaborate with others.
- Use features like **forks, pull requests (PRs), and issues**.

👉 Git = tool (on your computer).  
👉 GitHub = place to share/store code (online).

---

## 3. 🔹 Installing and Setting Up Git
Install Git from [https://git-scm.com/downloads](https://git-scm.com/downloads).  
Then configure it:

```bash
# Set your username (appears in commits)
git config --global user.name "Your Name"

# Set your email (use GitHub email for linking)
git config --global user.email "your-email@example.com"

# Check your configuration
git config --list
````

---

## 4. 🔹 Starting a Repository

### (A) Initialize a Local Repo

```bash
# Go to your project folder
cd my-project

# Initialize Git
git init
```

📌 This creates a hidden `.git/` folder to track changes.

### (B) Create a Repo on GitHub

1. Go to [GitHub](https://github.com).
2. Click **New Repository**.
3. Name it → Add description → Choose public/private.
4. Copy the HTTPS/SSH URL (needed to connect).

---

## 5. 🔹 Connecting Local Repo to GitHub (Remote)

```bash
# Add GitHub repo as remote
git remote add origin https://github.com/username/repo-name.git

# Check remote link
git remote -v
```

👉 `origin` is the default name Git gives to your GitHub remote.

---

## 6. 🔹 Adding and Committing Changes

```bash
# Stage files (prepare them for commit)
git add filename.txt
git add .       # adds all files

# Commit changes with a message
git commit -m "Initial commit"
```

* **`git add`** = marks files for commit.
* **`git commit`** = records a snapshot of your code.

---

## 7. 🔹 Pushing to GitHub

```bash
# Push your local commits to GitHub
git push -u origin main
```

* `origin` = remote name.
* `main` = branch name (older repos may use `master`).
* `-u` = links your local branch to remote, so later just use `git push`.

---

## 8. 🔹 Cloning a Repository

To copy a GitHub project onto your computer:

```bash
git clone https://github.com/username/repo-name.git
```

👉 This downloads the project with full Git history.

---

## 9. 🔹 Forking a Repository

* **Forking** = making your own copy of someone else’s GitHub repo.
* You can freely experiment, then make changes and propose them back.

Steps:

1. Go to the repo on GitHub.
2. Click **Fork** (top-right).
3. It appears in **your account**.
4. Now clone your fork locally with `git clone`.

---

## 10. 🔹 Pulling Latest Changes

If teammates updated the remote repo, bring changes to your local:

```bash
git pull origin main
```

👉 `git pull` = fetch + merge updates from GitHub.

---

## 11. 🔹 Branching Basics

### What is a Branch?

* A **branch** is like a parallel line of development.
* Default branch = `main`.
* Use branches to test features without breaking main code.

### Commands:

```bash
# Create a new branch
git branch feature-1

# Switch to branch
git checkout feature-1

# Create and switch in one step
git checkout -b feature-1

# See all branches
git branch

# Switch back to main
git checkout main
```

---

## 12. 🔹 Merging Branches

When finished with a feature:

```bash
# Go to main branch
git checkout main

# Merge feature branch into main
git merge feature-1
```

👉 If changes conflict, Git asks you to resolve them manually.

---

## 13. 🔹 Push Branch to GitHub

```bash
git push origin feature-1
```

Now others can see your branch online.

---

## 14. 🔹 Creating a Pull Request (PR)

A **Pull Request** = asking to merge your branch into main (or another repo).

Steps:

1. Push branch → Go to GitHub.
2. Click **Compare & Pull Request**.
3. Add title/description.
4. Submit for review.
5. Owner merges into main branch.

---

## 15. 🔹 Keeping Branch Updated

If `main` has new commits, update your branch:

```bash
git checkout feature-1
git pull origin main
git merge main
```

Or use **rebase** (advanced, cleaner history):

```bash
git checkout feature-1
git rebase main
```

---

## 16. 🔹 Summary of Important Commands

```bash
# Setup
git config --global user.name "Name"
git config --global user.email "Email"

# Initialize & connect
git init
git remote add origin <repo-url>

# Add & commit
git add .
git commit -m "Message"

# Push & pull
git push origin main
git pull origin main

# Clone & fork
git clone <repo-url>

# Branching
git checkout -b new-branch
git checkout main
git merge new-branch
git push origin new-branch

# View
git status
git log
git branch
```

---

## 🚀 Next Steps (Intermediate / Advanced)

* Learn **rebasing** and resolving conflicts.
* Explore **stash** to save temporary work:

  ```bash
  git stash
  git stash pop
  ```
* Use **.gitignore** to skip unwanted files.
* Explore GitHub Actions for CI/CD.
