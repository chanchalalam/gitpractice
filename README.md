
# Git Practice

This repository contains essential Git commands and workflows for cloning, branching, collaborating, fixing mistakes, and more. It serves as a practical guide to mastering Git from basic to advanced usage.

---

## Table of Contents

- [Cloning Your Repository](#cloning-your-repository)  
- [Basic Git Commands](#basic-git-commands)  
- [Creating a New Branch for a Task](#creating-a-new-branch-for-a-task)  
- [Branching & Collaboration Workflow](#branching--collaboration-workflow)  
- [Fixing Mistakes, Stashing Work, and Ignoring Files](#fixing-mistakes-stashing-work-and-ignoring-files)  
- [Forks, SSH, and CI/CD](#forks-ssh-and-cicd)  
- [GitHub CLI for Repo and PR Management](#github-cli-for-repo-and-pr-management)  

---

## Cloning Your Repository

1. Go to your repository on GitHub.  
2. Click the green **`<> Code`** button.  
3. Select **HTTPS** (or **SSH** if configured).  
4. Copy the URL, e.g.,  
   ```
   https://github.com/YourUsername/YourRepositoryName.git
   ```  
5. Open your terminal/Git Bash.  
6. Navigate to your desired local folder:  
   ```
   cd Documents/Projects
   ```  
7. Clone the repo:  
   ```
   git clone https://github.com/YourUsername/YourRepositoryName.git
   ```  

---

## Basic Git Commands


| Command                            | Description                                                    |
|----------------------------------|----------------------------------------------------------------|
| `git clone <repo-url>`            | Get a copy of a remote repository.                             |
| `git status`                     | See the state of your files (modified, staged, untracked).    |
| `git diff`                      | View exact changes made to files.                              |
| `git add <file>`                 | Stage changes for the next commit.                             |
| `git commit -m "message"`        | Commit staged changes with a descriptive message.             |
| `git push origin <branch-name>`  | Push your commits to the remote repository.                    |
| `git log`                       | View commit history.                                           |
| `git checkout <branch>`           | Switch branches.                                               |
| `touch CONTRIBUTING.md`           | Create a new file (example: CONTRIBUTING.md).                  |
| `git fetch`                     | Download changes from remote without merging.                  |
| `git pull`                      | Fetch and merge changes from remote to local branch.           |
| `git reset <file>`              | Unstage a file but keep changes locally.                        |
| `git reset --hard <commit>`      | Reset working directory and staging area to a specific commit (destructive). |
| `git rm <file>`                 | Remove a file from working directory and staging area.         |
| `git stash list`                | List all saved stashes.                                        |
| `git stash apply`               | Apply a stash without removing it from the stash list.         |
| `git branch`                   | List all local branches.                                       |
| `git branch -d <branch>`          | Delete a local branch if merged.                               |
| `git branch -D <branch>`          | Force delete a local branch even if unmerged.                  |
| `git remote -v`                 | Show URLs of remotes (fetch and push).                        |
| `git tag <tagname>`             | Create a tag for marking releases or important commits.        |
| `git show <commit/tag>`         | Show details of a commit or tag including diff and metadata.   |
| `git cherry-pick <commit>`       | Apply a commit’s changes to the current branch.               |
| `git blame <file>`              | Show who last modified each line in a file.                    |
| `git clean -f`                 | Remove untracked files from the working directory.             |
| `git diff --staged`                   | Show changes between staged files and last commit.          |
| `git merge <branch>`                  | Merge a branch into the current branch.                       |
| `git rebase <branch>`                 | Reapply commits on top of another base branch.               |
| `git reflog`                         | Show a log of all reference updates (including resets).      |
| `git remote add <name> <url>`         | Add a new remote repository with a given name.               |
| `git remote remove <name>`             | Remove a remote repository.                                  |
| `git tag -a <tag> -m "message"`       | Create an annotated tag with a message.                      |
| `git push origin --tags`               | Push all tags to remote repository.                          |
| `git revert --no-commit <commit>`      | Revert changes from a commit without committing immediately. |


---

## To Include Changes in a Commit

```bash
git add README.md
git commit -m "Update README with progress"
git push origin master
```

---

## Creating a New Branch for a Task

**Contribution Guidelines**

Thank you for considering contributing to this project!

### How to Contribute

1. Fork the repository.  
2. Create a new branch for your feature or bug fix.  
3. Make your changes.  
4. Submit a Pull Request.

### Steps to Work on a New Feature

```bash
# Check current branch and status
git status

# Create and switch to a new branch
git checkout -b feature-branch

# Create the CONTRIBUTING.md file
touch CONTRIBUTING.md

# Stage the new file
git add CONTRIBUTING.md

# Commit the file
git commit -m "Add CONTRIBUTING.md"

# Push the branch
git push origin feature-branch
```

---

## Branching & Collaboration Workflow

```bash
# Create a new branch locally
git checkout -b feature-1

# Add a new feature file
echo "This is a new feature file" > feature1.txt
git add feature1.txt
git commit -m "Add feature1.txt"

# Push the branch to GitHub
git push origin feature-1
```

- Go to your GitHub repo, click **Compare & Pull Request**, fill in details, and create the PR.  
- On GitHub, click **Merge pull request** and confirm the merge.  
- Sync your local master/main branch:

```bash
git checkout master
git pull origin master
```

---

## Fixing Mistakes, Stashing Work, and Ignoring Files

### Revert a Commit

```bash
# View commit history
git log --oneline

# Revert a commit (replace <commit-hash>)
git revert <commit-hash>

# Push changes
git push
```

### Stash Changes (Temporary Save)

```bash
git stash        # Stash your changes
git status       # Check status (should be clean)
git stash pop    # Restore stashed changes
```

### Create and Use `.gitignore`

```bash
# Create a .log file
echo "Ignore me" > test.log

# Add *.log to .gitignore
echo "*.log" >> .gitignore

# Stage and commit .gitignore
git add .gitignore
git commit -m "Ignore .log files"
git push
```

---

## Forks, SSH, and CI/CD

### Fork & Contribute to Any Public Repo

```bash
# Fork the repo on GitHub

# Clone your fork
git clone git@github.com:your_username/Hello-World.git
cd Hello-World

# Add upstream remote to track original repo
git remote add upstream https://github.com/octocat/Hello-World.git
git fetch upstream
git merge upstream/main  # or upstream/master
```

- Create a branch, make changes, push, and open a pull request from your fork.

### SSH Setup for Secure Pushes

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Copy your public key
cat ~/.ssh/id_ed25519.pub
```

- Add the copied key in GitHub → Settings → SSH and GPG keys → New SSH key.  
- Test SSH connection:

```bash
ssh -T git@github.com
```

### Add GitHub Actions for CI/CD

```bash
# Create workflow directory
mkdir -p .github/workflows

# Create workflow YAML file
touch .github/workflows/ci.yml
nano .github/workflows/ci.yml
```

- Paste your workflow config, save, then:

```bash
git add .github/workflows/ci.yml
git commit -m "Add basic GitHub Actions workflow"
git push
```

- View workflow runs in the **Actions** tab on GitHub.

---

## GitHub CLI to Manage Repos, Issues, and Pull Requests

```bash
# Install GitHub CLI
brew install gh

# Authenticate
gh auth login

# Clone a repo
gh repo clone chanchalalam/gitpractice
cd gitpractice

# Create a new issue
gh issue create --title "Test issue from CLI" --body "This is a test created via GitHub CLI"

# List open pull requests
gh pr list

# Create a new branch and PR
git checkout -b cli-feature
echo "CLI test" > cli.txt
git add cli.txt
git commit -m "Add cli.txt created via gh"
git push -u origin cli-feature
gh pr create --fill

# Review and merge PR
gh pr review <pr-number> --approve
gh pr merge <pr-number> --merge
```

---

