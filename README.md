## 🧩 CI/CD & Git Workflow Cheatsheet

From Contributing to Someone Else’s Repository (Forked Repo)
This guide outlines the repeating steps when contributing changes to a project where the original repository is already set as upstream.

## 🪄 1. Initial Setup (One-time Only)
#### 1. Fork the original repository on GitHub
####    (Click "Fork" on the original repo)

#### 2. Clone your fork to your local machine
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

###  3. Set Origin Repository pointing to your own accounts
git remote set-url origin https://github.com/<your-github-account>/<repo-name>.git

#### 3. Add the original repo as "upstream"
git remote add upstream https://github.com/<original-owner>/<repo-name>.git

#### 4. Verify remotes
git remote -v
#### Should show both origin (your fork) and upstream (original repo)

## 🔁 2. Repeating Steps Every Time You Contribute

### 🧭 Step 1. Sync Your Local Branch with the Upstream Main Branch
#### Switch to your main branch
git checkout main

#### Fetch the latest changes from the original repo
git fetch upstream

#### Merge them into your local main
git merge upstream/main

#### Push the updated main to your fork
git push origin main

### 🧩 Step 2. Create a New Feature Branch for Your Changes
#### Create and switch to a new branch
git checkout -b fix/your-feature-name

### 🧠 Step 3. Make Changes in Your Code
#### Edit, add, or delete files as needed
#### Once done, stage and commit your changes

git add .
git commit -m "Description of your changes"

### ☁️ Step 4. Push Your Branch to Your Fork
git push origin fix/your-feature-name

### 🔄 Step 5. Create a Pull Request (PR)
1.	Go to your forked repository on GitHub.
2.	You’ll see a “Compare & Pull Request” button — click it.
3.	Ensure the base repository is the original repo and the base branch is main.
4.	Add a short description and submit the pull request.

### 🧹 Step 6. After PR Is Merged
Once your PR is accepted and merged by the original repo’s maintainer:
#### Switch to your main branch
git checkout main

#### Pull the latest changes from upstream
git fetch upstream
git merge upstream/main

#### Push the updated main to your fork
git push origin main

#### Delete your local feature branch if done
git branch -d fix/your-feature-name

#### Delete remote branch from your fork if desired
git push origin --delete fix/your-feature-name

### 🧭 Notes
•	Always create a new branch per feature or fix — never code directly on main.
•	If your branch becomes outdated before your PR is merged:
    git fetch upstream
    git rebase upstream/main
•	Keep commits small and meaningful.
•	Use clear, descriptive PR titles.





