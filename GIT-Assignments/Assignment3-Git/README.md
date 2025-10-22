🌿 Git Branching and Remote Management

📘 Objective

This project demonstrates Git branching operations, committing changes in different branches, pushing them to GitHub, and managing branch deletions locally and remotely.

🧩 Tasks Performed
✅ 1. Create a Git Working Directory
mkdir git-branching-task
cd git-branching-task
git init

✅ 2. Create and Commit File in master Branch
echo "This is main file" > main.txt
git add main.txt
git commit -m "Add main.txt in master branch"

✅ 3. Create Branches
git branch develop
git branch f1
git branch f2


You can verify the branches using:

git branch

✅ 4. Add and Commit Files in Each Branch
🌱 Develop Branch
git checkout develop
echo "This is develop branch file" > develop.txt
git add develop.txt
git commit -m "Add develop.txt in develop branch"

🌿 F1 Branch
git checkout f1
echo "This is f1 branch file" > f1.txt
git add f1.txt
git commit -m "Add f1.txt in f1 branch"

🍃 F2 Branch
git checkout f2
echo "This is f2 branch file" > f2.txt
git add f2.txt
git commit -m "Add f2.txt in f2 branch"

🚀 5. Push All Branches to GitHub

Add your remote repository and push all branches:

git remote add origin <your-repo-URL>
git push origin master
git push origin develop
git push origin f1
git push origin f2


You can confirm all branches on GitHub by visiting your repository page.

🗑️ 6. Delete f2 Branch Locally
git branch -d f2


(Use -D instead of -d to force delete if not fully merged.)

❌ 7. Delete f2 Branch from GitHub
git push origin --delete f2

📂 Project Summary
Step	Description	Status
Initialize repo	git init	✅
Create branches	develop, f1, f2	✅
Commit files	Added unique file to each branch	✅


Push to GitHub	All branches pushed	✅
Delete branch	f2 deleted locally and remotely	✅
