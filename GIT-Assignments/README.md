Git Assignment README
Assignment Overview

This directory contains tasks and exercises related to Git version control, including branching, merging, stashing, and pushing to GitHub. The objective is to practice and demonstrate proficiency in Git operations.

Repository Structure

git-assignment
│
├── master.txt              # File committed on master branch
├── public1.txt             # File committed on public1 branch
├── public2.txt             # File committed on public2 branch
├── develop.txt             # File committed on develop branch
├── feature1.txt            # File committed on feature1 branch
├── feature2.txt            # File committed on feature2 branch
└── README.md               # This README file

Tasks Performed

Branching

Created multiple branches (develop, feature1, feature2, public1, public2, private).

Committed files to their respective branches.

Merging

Merged public1 and public2 branches into master.

Handled merge conflicts where applicable.

Stashing

Stashed changes in one branch and applied them to another.

GitHub Integration

Pushed all branches to GitHub.

Deleted local and remote branches as required.

Commands Used (Examples)
# Clone repository
git clone <repo-url>

# Create and switch to branch
git checkout -b feature1

# Add files and commit
git add feature1.txt
git commit -m "Added feature1.txt"

# Merge branches
git checkout master
git merge feature1

# Stash changes
git stash
git checkout feature2
git stash apply

# Push to GitHub
git push origin master
git push origin feature1

# Delete branch
git branch -d feature2
git push origin --delete feature2
