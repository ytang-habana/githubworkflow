
# Git Workflow Guide

## Step 1: Pull Repo from GitHub to Local
```sh
git clone https://github.com/ytang-habana/githubworkflow.git
```

## Step 2: Create a Feature Branch (or Hotfix Branch)
```sh
git checkout -b hotfix
```

## Step 3: Make Changes on Hotfix Branch
```sh
git add changed_files
git commit
```

## Step 4: Push Hotfix Branch to GitHub
```sh
git push origin hotfix
```

At the same time, the GitHub `main` branch may have some new changes, so you need to pull the updates.

## Step 5: Update the Local Main Branch with the Most Recent Updates from GitHub
```sh
git checkout main
git pull origin main
```

## Step 6: Apply the Updates in `main` to the Hotfix Branch and Resolve Conflicts
```sh
git checkout hotfix
git rebase main  # Resolve conflicts if necessary
```

## Step 7: Push Back the Most Recent Hotfix Branch to GitHub
```sh
git push -f origin hotfix
```

## Step 8: Create a Pull Request in GitHub
A new pull request is created in GitHub. Fill out the comments and descriptions, and ask the repo owner and contributors to review the code.

## Step 9: Merge the Pull Request
After the code review passes, the repo owner will merge (and squash if possible).

## Step 10: Delete the Hotfix Branch
After merging, the repo owner or you need to delete the hotfix branch in GitHub:
```sh
git push origin --delete hotfix
```
Also, delete the hotfix branch locally:
```sh
git branch -D hotfix
```

## Step 11: Sync `main` to Your Local
```sh
git pull origin main
```


