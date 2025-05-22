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


## To tell Git to include these modifications in the next commit

step1: git add README.md
step2: git commit -m "Update README with progress"
step3: git push origin main
