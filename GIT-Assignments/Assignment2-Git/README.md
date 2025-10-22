🚀 Git Branching and Stashing Exercise
📘 Objective

This exercise demonstrates how to:

Work with multiple Git branches

Stage and commit files

Use the stash feature to temporarily store uncommitted changes

🛠️ Steps and Commands
1️⃣ Create a Git working directory and initialize the repository
mkdir GitBranchingTask
cd GitBranchingTask
git init

2️⃣ Create files in the master branch
echo "This is feature1 file" > feature1.txt
echo "This is feature2 file" > feature2.txt

3️⃣ Stage and commit the files
git add feature1.txt feature2.txt
git commit -m "Added feature1.txt and feature2.txt to master branch"

4️⃣ Create three new branches: develop, feature1, and feature2
git branch develop
git branch feature1
git branch feature2


✅ Check your branches:

git branch

5️⃣ Switch to the develop branch
git checkout develop

6️⃣ Create a new file develop.txt (do not stage or commit)
echo "This is the develop branch file" > develop.txt

7️⃣ Stash the file
git stash


💡 This temporarily saves your uncommitted work so you can switch branches safely.

8️⃣ Checkout to the feature1 branch
git checkout feature1
9️⃣ Create a new file new.txt, then stage and commit it
echo "This is a new file in feature1 branch" > new.txt
git add new.txt
git commit -m "Added new.txt in feature1 branch"

🔟 Checkout back to the develop branch
git checkout develop

1️⃣1️⃣ Unstash the previously stashed file
git stash pop

1️⃣2️⃣ Stage and commit the unstashed file
git add develop.txt
git commit -m "Added develop.txt after unstashing"

🧾 Summary of Commands
Step	Description	Command
1	Initialize Git repo	git init
2	Create files	echo "text" > filename.txt
3	Stage and commit	git add filename.txt && git commit -m "message"
4	Create branches	git branch develop feature1 feature2
5	Switch branches	git checkout branch_name
6	Stash changes	git stash
7	Unstash changes	git stash pop
8	View branches	git branch
🏁 Conclusion

This task successfully demonstrates:

Creating and managing branches

Using git stash to save uncommitted work

Switching between branches and merging workflow updates

🧠 Pro Tip

If you ever lose track of stashes, use:

git stash list


And to apply without deleting from stash:

git stash apply

