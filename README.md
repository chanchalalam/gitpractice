# gitpractice
## How to Clone Your Repository

Go to your repository on GitHub.

Click the green "<> Code" button.

Make sure "HTTPS" is selected (or "SSH" if you've set up SSH keys – HTTPS is simpler for now).

Copy the URL. It will look something like https://github.com/YourUsername/YourRepositoryName.git.

Open your terminal/Git Bash.

Navigate to the directory where you want to store your project locally (e.g., cd Documents/Projects).

Run the clone command:git clone
https://github.com/YourUsername/YourRepositoryName.git

git status: Run git status

git diff README.md: View the differences  

git clone: Get a copy of a remote repository.

git status: See the state of your files (modified, staged, untracked).

git add <file>: Stage changes for the next commit.

git commit -m "message": Save a snapshot of your staged changes to your local history.

git push origin <branch-name>: Send your local commits to the remote repository on GitHub.

git diff: See the exact changes you've made to files.

git log: View the commit history .

git checkout master: To Switch the branch

touch CONTRIBUTING.md: Create the CONTRIBUTING.md file

## To tell Git to include these modifications in the next commit

step1: git add README.md

step2: git commit -m "Update README with progress"

step3: git push origin main

## Create a New Branch for a New Task 
 Contribution Guidelines
Thank you for considering contributing to this project!
 How to Contribute
1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes.
4. Submit a Pull Request.

Step 1: Check current branch and its status
Step 2: Create and switch to a new feature branch
Step 3: Attempt to add a file that doesn't exist yet
Step 4: Create the CONTRIBUTING.md file
Step 5: Stage the newly created file
Step 6: Commit the staged file to the feature branch
Step 7: Push the new branch and its commit to the remote repository


## Branching & Collaboration

Step 1: Create a New Branch Locally(git checkout -b feature-1
)
 Step 2: Add a New Feature File(echo "This is a new feature file" > feature1.txt
git add feature1.txt
git commit -m "Add feature1.txt")
Step 3: Push the Branch to GitHub(git push origin feature-1
){Go to your GitHub repo. We will see
➡️ "Compare & Pull Request" → Click it → Fill in title & description → Create Pull Request.}
Step 4: Merge the Pull Request( On the GitHub UI, click Merge pull request.Click Confirm merge.)
Step 5: Sync Local master or main(git checkout master
git pull origin master
)

##  Fixing Mistakes, Stashing Work, and Ignoring Junk
### Revert a Commit in Git
Step1: See the commit history(git log --oneline)
{It will show something like:a1b2c3d Add mistake.txt}
Step2: Revert the commit(git revert a1b2c3d)
Step3:git push
### Stash Changes (temporary save)
Step1: Stash your work(git stash)
Step2: Your changes are now hidden! Check status(git status)
Step3: Bring the changes back(git stash pop)
### .gitignore creating
Step1: Create a .log file and ignore it(echo "Ignore me" >test.log)
Step2: echo "*.log" >> .gitignore
Step3: git add .gitignore
Step4: git commit -m "Ignore .log files"
Step5: git push

## Forks, SSH, and CI/CD
### Fork & Contribute to Any Public Repo
Step1: Go to any public repo  → click Fork.
Step2: Clone your fork(git clone git@github.com:your_username/Hello-World.git
cd Hello-World)
Step3: Add upstream to track the original repo(git remote add upstream https://github.com/octocat/Hello-World.git
git fetch upstream
git merge upstream/main  # or upstream/master)
Step4: Create a branch, make changes, push, and open a pull request from your fork → base repo.
### SSH Set Up for Secure Pushes
Step1: Generate SSH Key (ssh-keygen -t ed25519 -C "your_email@example.com"){Press Enter through prompts (or add a custom file path).
Step2: This creates a key pair: ~/.ssh/id_ed25519 and ~/.ssh/id_ed25519.pub.}
Step3: Add SSH Key to GitHub:(cat ~/.ssh/id_ed25519.pub){Copy the entire key (starts with ssh-ed25519).
Go to GitHub → Settings → SSH and GPG Keys → New SSH Key.
Give it a name like laptop-key and paste the key.}
Step4: Test your connection(ssh -T git@github.com)
###  Add GitHub Actions (CI/CD)
Step 1: Create Workflow Directory(mkdir -p .github/workflows)
Step 2: Create a Workflow File(Create a YAML file inside the folder:touch .github/workflows/ci.yml,Now Open:nano .github/workflows/ci.yml, And paste :Someline and to save and exit ((Ctrl + O, Enter, then Ctrl + X in nano)
Step 3: Commit and Push the Workflow (git add .github/workflows/ci.yml
git commit -m "Add basic GitHub Actions workflow"
git push)
Step 4: View the Workflow Run{Go to your repo on GitHub,Click the Actions tab,You’ll see your workflow (CI Workflow) running,Click on it to view logs and steps}

## GitHub CLI to manage repos, issues, pull requests, and more

Step 1: Install GitHub CLI(brew install gh)
Step 2: Authenticate(gh auth login)
Step 3: Try basic commands(gh repo clone chanchalalam/gitpractice ,cd gitpractice)
Step4: Create a new issue:gh issue create --title "Test issue from CLI" --body "This is a test created via GitHub CLI"
Step5: List open PRs:gh pr list
Step6: Create a new branch & PR{git checkout -b cli-feature
echo "CLI test" > cli.txt
git add cli.txt
git commit -m "Add cli.txt created via gh"
git push -u origin cli-feature
gh pr create --fill}
Step7:Review and merge PR{gh pr review <pr-number> --approve
gh pr merge <pr-number> --merge}

