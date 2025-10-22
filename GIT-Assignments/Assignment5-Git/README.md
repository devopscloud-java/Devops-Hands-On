Step 1: Initialize Git Repository
mkdir gitflow_project
cd gitflow_project
git init


This creates a new Git repository.

Step 2: Create the Git Flow branches

Git Flow generally includes:

master → Production-ready code

develop → Integration branch for features

feature/* → Feature branches

release/* → Optional for preparing releases

hotfix/* → For urgent fixes on master

# Ensure you are on master
git checkout -b master

# Create develop branch
git checkout -b develop

# Create a feature branch
git checkout -b feature/login

Step 3: Work on Feature Branch

Add a file in the feature branch:

echo "Feature work" > feature.txt
git add feature.txt
git commit -m "Add feature.txt in feature branch"

Step 4: Merge Feature into Develop
git checkout develop
git merge feature/login

Step 5: Merge Develop into Master
git checkout master
git merge develop

Step 6: Hotfix on Master

Create a hotfix branch from master:

git checkout -b hotfix/urgent
echo "Urgent fix applied" > urgent.txt
git add urgent.txt
git commit -m "Add urgent.txt via hotfix"


Merge hotfix back into master and develop:

git checkout master
git merge hotfix/urgent

git checkout develop
git merge hotfix/urgent

Step 7: Push Branches to Remote
git remote add origin <your-github-repo-url>

# Push all branches
git push -u origin master
git push -u origin develop
git push -u origin feature/login
git push -u origin hotfix/urgent

Step 8: Simple README file
echo "# Git Flow Project" > README.md
git add README.md
git commit -m "Add simple README file"
git push origin master


✅ Summary:

feature/login → Added feature, merged to develop.

develop → Integrated features, merged to master.

hotfix/urgent → Created urgent fix, merged to master & develop.


