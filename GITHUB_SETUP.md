# Publish Dave's Fry Catch to GitHub

Open Terminal on your Mac and paste the commands below.

## 1. Install and sign in to GitHub CLI

```bash
brew install gh
gh auth login --web --git-protocol https
```

Your browser will open so you can authorize GitHub CLI. After authorization,
return to Terminal.

## 2. Create and publish the repository

Paste this entire block:

```bash
cd "/Users/ttvaroh/Desktop/Code/mini projects/c1-summit"

git init -b main
git add .
git commit -m "Build Dave's Fry Catch arcade game"

gh repo create daves-fry-catch \
  --private \
  --description "Built as part of the Capital One Tech Summit, with some creative liberty applied to its falling coin catch design spec: an arcade-style game where you catch the best french fries—Dave's Hot Chicken fries." \
  --source=. \
  --remote=origin \
  --push
```

This creates a **private** repository named `daves-fry-catch`.

To make it public immediately, replace `--private` with `--public` before
running the command.

## 3. Open the finished repository

```bash
gh repo view --web
```

## If Git asks who you are

Run the following with your real GitHub name and account email, then repeat the
commit and repository-creation commands:

```bash
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR_GITHUB_EMAIL"

git commit -m "Build Dave's Fry Catch arcade game"

gh repo create daves-fry-catch \
  --private \
  --description "Built as part of the Capital One Tech Summit, with some creative liberty applied to its falling coin catch design spec: an arcade-style game where you catch the best french fries—Dave's Hot Chicken fries." \
  --source=. \
  --remote=origin \
  --push
```
