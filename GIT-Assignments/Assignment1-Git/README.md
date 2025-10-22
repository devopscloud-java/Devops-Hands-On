Git Operations Task
📘 Objective

This task demonstrates the basic Git operations — creating a repository, staging files, committing changes, and pushing them to GitHub.

🧩 Steps Performed
1. Create a new folder
mkdir GitTask
cd GitTask

2. Create the required files
echo "This is the code file" > Code.txt
echo "This is the log file" > Log.txt
echo "This is the output file" > Output.txt

3. Initialize a new Git repository
git init

4. Stage the required files

Only Code.txt and Output.txt need to be staged.

git add Code.txt Output.txt

5. Commit the staged files
git commit -m "Added Code.txt and Output.txt files"

6. Connect to GitHub repository

(Replace <your-repo-url> with your actual GitHub repository link)

git remote add origin <your-repo-url>

7. Push the committed files to GitHub
git branch -M main
git push -u origin main

✅ Files in the Folder

Code.txt

Log.txt

Output.txt

🧠 Notes

git status can be used anytime to check which files are staged or untracked.

Ensure you have set your GitHub credentials using:

git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
