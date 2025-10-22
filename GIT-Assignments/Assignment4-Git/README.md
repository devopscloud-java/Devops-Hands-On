Git Branching and Merging Workflow
Step 1: Create repository and commit master.txt
# Initialize a new Git repository
git init

# Create master.txt and add some content
echo "This is master file" > master.txt

# Stage and commit
git add master.txt
git commit -m "Add master.txt to master branch"

Step 2: Create branches
git branch public1
git branch public2
git branch private

Step 3: Add public1.txt to public1 branch
# Switch to public1 branch
git checkout public1

# Create file and commit
echo "This is public1 file" > public1.txt
git add public1.txt
git commit -m "Add public1.txt to public1 branch"

Step 4: Merge public1 into master
# Switch to master branch
git checkout master

# Merge public1
git merge public1 -m "Merge public1 branch into master"

Step 5: Merge public2 into master
# Switch to public2 branch
git checkout public2

# Create public2.txt (if not created already)
echo "This is public2 file" > public2.txt
git add public2.txt
git commit -m "Add public2.txt to public2 branch"

# Switch back to master
git checkout master

# Merge public2
git merge public2 -m "Merge public2 branch into master"

Step 6: Edit master.txt on private branch
# Switch to private branch
git checkout private

# Edit master.txt
echo "Updated content on private branch" >> master.txt

# Stage and commit changes
git add master.txt
git commit -m "Update master.txt on private branch"

Step 7: Update public1 and public2 with new private changes
# Update public1 branch with private changes
git checkout public1
git merge private -m "Update public1 with latest private changes"

# Update public2 branch with private changes
git checkout public2
git merge private -m "Update public2 with latest private changes"

Step 8: Update master with private changes
git checkout master
git merge private -m "Update master branch with private changes"

Step 9: Update private branch with all new changes
git checkout private
git merge master -m "Sync private branch with latest master changes"


✅ Notes:

Always check for conflicts during merges and resolve them.

Use git status to confirm branch and staged changes.

Commit messages should be descriptive of changes.


