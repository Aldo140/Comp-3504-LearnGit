Work in pairs and make one submission with both names included in your submission text. You only need to submit answers to the items written in blue (there are 3 of them!). 

**All commands here are linux-based commands. If you are working in a different environment, you may need to modify them for your context**


Git Basics


Create a folder in your computer and then move to this folder:

mkdir learnGit
cd learnGit

Check all files (including hidden files in this folder):
	ls -al

Make this folder to be a git repository:
	git init

Now, check all files (including hidden files in this folder) again:
ls -al

Did you notice any changes? 

Check inside of the .git folder:
ls -al .git/

What is the role of the folders you see?
HEAD
config
hooks
objects
refs
heads
tags

Check the status of the repository:
git status

Check the branches that exist in your repository:
	git branch

Check your git history of your repository:
	git log

Check the branch pointers in your refs/heads folder
	ls .git/refs/heads/

Create a file in your repository, write some text about your personal interests and then stage the file:

touch file1.txt
git add file1.txt

View the status of your repository:
git status

Now, commit the changes to the repository. Make sure to use a proper git message:

	git commit -m “Joe’s personal interests are added”

After your commit, revise the following items:
Check the branches that exist in your repository
Check the history of your repository
Check the branch pointers in your refs/heads folder
Check what is inside your main reference
cat .git/refs/heads/main

Do you see a relation between your commits and what is stored in your branch head reference?

Create another file in your repository, write some text about your teammate’s interests and then stage the file:

touch file2.txt
git add file2.txt

Make some changes to file1.txt by writing about courses you are taking:

View the status of your repository:


View the changes in file1:
	git diff file1.txt
Stage change in file1.txt

If you commit changes now, the changes in two files will be committed. What if we want to commit these files separately. Then, we must unstage the files that we do not want to commit:

git restore --staged file1.txt
 Confirm your action by viewing the status of the repository:


Now, commit changes in your file 2  with a proper message.

Stage and commit changes in file1 with a proper message.

View the history of your repository:
What is the long string you see for each commit?
What else is visible in the history of your commit?
Do we need to add the date or developer’s name to the commit message?
Based on your information about git history, what would be a good commit message?
When you have many commits in the repository, it might be helpful to see a shorter version of the log. Try this command:
git log --oneline

Where are the HEAD and main references referring to?

Git stores different versions of our files. Can we move to old versions of the files in the repository?


Checkout a version of the history before first student's course info being added to file 1:
git checkout <<SHA>>

What does the message “HEAD detached at <<SHA>>” that you see mean?


Where is the main branch reference? 
	git log

View the history of your main branch:
git log main

HEAD and main references are referring to different points. Now, run this command and explain what is happening?
	git checkout main





Make some changes in file2. Before staging, you want to remove changes made to this file:
git checkout file2.txt

Make some changes in file2. Staging it, now you want to remove changes made to this file. You can unstage it and then revert the changes:

git restore --staged file2.txt
git checkout file2.txt


Report: Discuss and summarize your learning in 1-2 paragraphs:






Git Branches

Create a new branch and switch to it:

git checkout -b featureA


List all references in your refs/head folder of .git
ls .git/refs/heads/

List all branches in the repository, and see which branch is selected?


View the content of the HEAD file. Is there a relationship between the content of this file and the selected branch?
cat .git/HEAD


Create a new file in your new branch and write some information about your neighbor team in that file. Stage and commit this with a proper message.

Make some changes to the information of student 2 in file2 in your new branch by adding the courses they take. Stage and commit this with a proper message.


Make some changes to the information of student 1 in file1 in your new branch by adding the information on programming languages they know. Stage and commit this with a proper message.


View the log of the repository, and explain the reason for different places that HEAD, main, and featureA references are referring to:
git log


Switch to the main branch. Do you see the changes to the files1, 2 and 3 in this branch?


What if we want to bring (merge) changes we made in the new branch into this branch? We can bring all changes at the same time. But, let’s practice bringing selected changes:

Let’s add the first commit related to the other team’s info to your main branch:
git cherry-pick <SHA>

Let’s fully merge featureA branch into our main branch

git merge featureA


In the main branch create a new file, file4.txt, and write some text about your shared friend. Do not stage or commit this file. Switch to your featureA where it should not have this new file.

View the list of files in featureA branch:
ls -al

Why do you see file4.txt in this branch?

How could you prevent file4 from showing up in your other branches, when you switch?

Come back to your main branch. Now, stage your changes. Then, stash changes, and then move to the featureA branch. 

git add file4.txt
git stash

Do you see file4 in featureA branch?

Go back to your main branch. List all files. Do you see your file4.txt? 


List all stashed items in this branch
git stash list

Now, pop the stashed item
	git stash pop

List all files in your directory and all stashed items. Explain what you see:
git stash list
ls


Report:  Discuss and summarize your learning in 1-2 paragraphs:






Connect your repository to a remote repository


Create a remote repository on Github.

Then, connect your local repository to this remote repository.

	git remote add origin <<address of your remote repository>>

Push the changes from your main and featureA branches to your remote repository.



Report:  Discuss and summarize your learning in 1-2 paragraphs:
