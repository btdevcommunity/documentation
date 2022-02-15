# <p align="center">Introduction to GitHub</p>

## What is Git?
Git is a free and open-source distributed version control system designed originally by Linus Torvalds.
## Difference Between Github and Git?

<!--  Use mark down table-->

## What is GitHub?
GitHub is an internet hosting provider for the software development and version control system using Git. It offers the distributed version control and source code management (SCM) functionality of Git and its own additional features.

## Best Features of GitHub:
 - Access control 
 - Bug tracking
 - Features request
 - Task management
 - Continuous integration
 - Wikis

Used by:
- Open Source project (Public Repositories)
- Corporates and companies to host their code in private repository 

# Configure and using Git and GitHub

## Step 0: Install Git and create an account in Github.

You need to install Git in your system and create a GitHub account. All git commands are the same for Windows, Mac and Linux.

To install Git follow the directions on the git-scm site and there is nothing for you to configure manually, just click next and proceed with the installation once you download it.

Git - Download Site - https://git-scm.com/downloads

Once you have installed Git, you can create a free account on GitHub from the link below. https://github.com/signup

We will be using Git commands and if you are unfamiliar with it, you may explore more from the link below.

https://ubuntu.com/tutorials/command-line-for-beginners

Some basic commands that we will be using are:
1. cd - Change directory 
2. mkdir - Create new directory
3. ls - List the contents of the directory
4. pwd - View the present working directory
5. touch - Create files

## Step 1: Create local git repository 
When creating a new project in your local machine using git, you will create a repository also known as a repo in short.

For Windows:
Right Click on the directory where you want to create the repository and click ‘Git Bash Here’
<!--  link image from our server-->

For Mac and Linux:
Open Git Bash or Terminal and go to the directory in which you want to create the local repository using cd (change directory) command. This can also be done in windows.

<!--  link image from our server-->

To begin moving to your working directory use the cd command if you haven't clicked 'Git Bash Here’ in windows. For Mac and Linux operating systems, you may follow this until you reach your desired directory. 

Once you are in your desired directory, you may create the project directory by using mkdir command and get inside the project directory.

- $ cd /d - (To move to your desired directory. Letter “d” is the drive name)
- $ mkdir new_project - (Create a new directory called new_project)
- $ cd new_project - (Move into the new_project directory) 

<!--  link image from our server-->

To initialize a git repository in the root of the folder, run the git init command:

<!--  link image from our server-->

Once you run the git init command, you get some hints and a command at the end showing that the git repository is initialized in your particular directory.

## Step 2: Add new files to the repository

You can create new files using your desired text editor or via touch command.
<!--  link image from our server-->

README.md is a markdown file that contains the details of your repository or project.
The ls command shows the lists of files in the current directory

The git status command gives you the current state of the project including all commits, stages and the files tracked by git.

<!--  link image from our server-->

Here, the git status command says that you have created a file called README.md but it says it's untracked and you haven't added it to a branch to be tracked. It won't be added to the git branch and get tracked unless you use the  git add command.

## An interlude: The staging environment, the commit and you.

Most of the users get confused when they first learn the git concepts of staging environment and how it relates to a commit.

A commit is a record of when and what you did in the last state or change in the project. 
For example, if you add a file or modify a file in your repository you tell git to put those changes into a commit.

The staging environment tells which changed file to push in a commit. As seen in step 2, creating a file doesn’t do anything to a commit even when we know that a file has been created.

To add a file to a commit,  first, you need to add it to the staging environment.
- $ git add <file name> which will be done in step 3

Note: The staging environment, also called “staging” is the preferred term but it is also referred to as “indexing”.
## Step 3: Add a file to the staging environment

Add a file to the staging environment by using the $ git add <filename with extension> command.
  
If you see the git status the file has not been committed yet but the file has been staged for now.
  
<!--  link image from our server-->

## Step 4: Create a commit

Run a command $ git commit -m <Your commit message> to create a commit from your staged file.

<!--  link image from our server-->

The message at the end of the command should be something related to the commit contained, it can be a new feature, bug fixes or typos. Don’t put a message like “ashajsdhgf” or “updates”. This is because other programmers going through your project won't be understanding what changes you made in the commit. Commit lives forever in the repository and if you leave a meaningful commit message it will help other programmers to understand easily or it can be you in future who want to figure out why this change was made years later.

## Step 5: Create new branch

Branches allow you to develop features, fix bugs, or safely experiment with new ideas in a contained area of your repository. The Master branch is the first branch made when you initialize a Git repository. All repositories must have a master branch.

If you want to add new features on a branch without combining the new codes with previous versions or without combining codes with the master branch to prevent errors you may create new branches. Git branch comes in handy in these situations where you will be working on new features in a separate branch without making changes to the main branch.

Branch allows you to move back and forth between “states” of your project. For example, if you want to develop a website about a restaurant that becomes the main branch. If you want to develop a menu bar, you can create a branch name menu where you will develop a menu on the menu branch. When you finish developing it you can merge it to the main branch. When you create a branch git keeps track of which commit you “branched” off of, it maintains a history of what has happened over time.

To create a new branch use checkout command $ git checkout -b <name of new branch>
This command will automatically create a branch and check you out to that branch, meaning, git will move you to that branch, off from the primary or main branch.
<!--  link image from our server-->
 
Use the git branch command to see your branch details.
<!--  link image from our server-->

The branch name with an asterisk indicates which branch you are currently at the moment.

Note: By default, every git repository’s first branch is the master branch and is named as the “main” branch primary branch in a project.

## Step 6: Create a new repository on GitHub

If you only want to keep track of your project in your local environment, you don’t need to use GitHub. But if you would like to work in a team, you can use GitHub to collaboratively modify the project code.

First, Login to GitHub and you will see your dashboard similar to this.

<!--  link image from our server-->

To create a new repository on your GitHub, go to the Repositories tab in your dashboard and click on New (green button)

<!--  link image from our server-->

After clicking on the New button, GitHub will ask you to provide the name of the repository and give a brief description about it.

<!--  link image from our server-->

When you are done filling out the information click on the Create repository button.

Then, GitHub will ask you to create the repo from scratch or to add a repo locally. In this case, we have already created a new local repository so we will follow the “... or push an existing repository from the command line” 

<!--  link image from our server-->

<!--  link image from our server-->

Once you get your own repository link, you can paste it in your bash and add origin using $ git remote add origin <your repo link> command. You need to specify the branch you are pushing to by using the $ git branch -M main command.

Finally, you push your commit by using  $ git push -u origin main. This command will push the local repository to Github

Note: 
Repository Link should be yours when you add origin in bash
Refresh your GitHub page you will see your local repository pushed successfully 
<!--  link image from our server-->

## Step 7: Push a branch to GitHub

Now we will push the local branch which we have created to the GitHub repository.
If your branch is approved by the repository owner (In this case you are the owner so you can approve yourself), s/he will merge it to the main branch.

To push changes onto a new branch on GitHub
Run this command: $ git push origin <your branch name>
<!--  link image from our server-->

You can see now that two branches are pushed to the GitHub repository from our local repository.

<!--  link image from our server-->

Note: If this is your first time using GitHub locally then it might prompt you to log in to GitHub username and password.

## Step 8: Create a pull request (PR)

Pull request is a way to notify the repository owner that you need to make some changes in their primary branch.

For example, we will make some changes in our menu branch and pull request in the main branch in our repo to get merge. (Since this is on our repository same working principle is applied in other repositories).

You can see here that the README.md file has been modified via text editor and is committed to the menu branch.

<!--  link image from our server-->

Again push the menu branch from the local repo to GitHub.

<!--  link image from our server-->

You can see that the GitHub menu branch is updated now.

<!--  link image from our server-->
  
Now we will pull the request and merge it to the main branch.
Click on the pull request tab and click on compare and pull request.

<!--  link image from our server-->

Now fill up the information in the comment section and assign yourself (In a team project you will assign others too).
Labels as documentation (since we are updating the readme file which is serving as a document for what the project is about).
For the reviewer leave blank (In a team you will assign a reviewer to review your changes).
Click on create pull request.

<!--  link image from our server-->

## Step 9: Merge a PR
Now click on merge pull request. This will merge the changes into the primary branc.h

<!--  link image from our server-->
 
You will see this message after successfully merging to the primary branch.

<!--  link image from our server-->

Click on the commit tab where you can see the hash code of the commit. Hash code is a unique identifier of that specific commit. It is useful to refer to specific commits and when undoing changes(use the git revert <hash code> command to backtrack).

<!--  link image from our server-->

## Step 10: Get GitHub changes to your local machine (We haven't done any changes in the GitHub repository in this case. For instance if you are working in a team the repository get updates on Github so you need to get changes to your local machine )

For this case we will directly edit the main branch README.md file and add a new line and merge it. You can easily edit the file in the GitHub interface by clicking on the pencil icon.

<!--  link image from our server-->

Files have been updated by committing from the GitHub interface (Not recommended but you can commit from here too. Use Visual Code Editor which has a built-in git version control to make changes from your local machine ).

<!--  link image from our server-->

Now we will fetch these changes to our local repository.
Run this command: git pull origin main

<!--  link image from our server-->

Now check the git log command to see all the changes committed. 

 <!--  link image from our server-->

Note: It is recommended to delete the branch after merging into the primary branch as it may get confusing with multiple branches..

Additional command
 - Switch branch: git checkout <name of branch>
 - Delete branch: get branch -d <name of branch>

### Yay! You made it.

Additional Resources
 - https://training.github.com/
 - https://learngitbranching.js.org/
 - https://github.com/arslanbilal/git-cheat-sheet
