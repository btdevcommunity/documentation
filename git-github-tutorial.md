# <p align="center">Introduction to GitHub</p>

</br>

## What is Git?

***Git*** is a free and open-source distributed *version control system* designed originally by Linus Torvalds.

</br>

## Difference Between Github and Git

| GitHub                                     | Git                                                        |
| ------------------------------------------ | ---------------------------------------------------------- |
| Github is a service.                       | Git is software                                            |
| Github is a graphical interface            | Git is a command-line tool.                                |
| Github is hosted on the web.               | Git is installed locally in the system.                    |
| Maintained by Microsoft.                   | Maintained by Linux.                                       |
| Centralized source code hosting.           | Version control and code sharing.                          |
| Is a hosting service for Git repositories. | Is a version control system to manage source code history. |
| Launched in 2008.                          | Released in 2005.                                          |
| Built-in user management system.           | No user management feature.                                |

</br>

## What is GitHub?

***GitHub*** is an internet hosting provider for the software development and version control system using *Git*. It offers the distributed version control and source code management (SCM) functionality of Git and its own additional features.

## Best Features of GitHub:

- Access control 
- Bug tracking
- Features request
- Task management
- Continuous integration
- Wikis

**Used by:**

- Open Source project (Public Repositories)
- Corporates and companies to host their code in private repository 

</br>

## Configure and using Git and GitHub

</br>

## Step 0: Install Git and create an account in Github.

You need to install `Git` in your system and create a `GitHub` account. All git commands are the same for Windows, Mac and Linux.

To install `Git` follow the directions on the [git-scm](https://git-scm.com) site and there is nothing for you to configure manually, just click next and proceed with the installation once you download it.

`Git` - [Download Site](https://git-scm.com/downloads)

Once you have installed Git, you can create a free account on GitHub from the link below. 

`GitHub` - [Join · GitHub](https://github.com/signup)

We will be using *Git* commands and if you are unfamiliar with it, you may explore more from the link below.

`Commands` - [Git commands for beginners | Ubuntu](https://ubuntu.com/tutorials/command-line-for-beginners)

Some basic commands that we will be using are:

1. `cd `- *Change directory*
2. `mkdir` - *Create new directory*
3. `ls` - *List the contents of the directory*
4. `pwd` - *View the present working directory*
5. `touch` - *Create files*

</br>

## Step 1: Create local git repository

When creating a new project in your local machine using git, you will create a repository also known as a repo in short.

*For Windows:*
Right Click on the directory where you want to create the repository and click `Git Bash Here`

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/1_git_bash_options.png" alt="Git Bash Option" height="370px" width="298px"/>
 </a>
</p>

*For Mac and Linux:*
Open `Git Bash` or `Terminal` and go to the directory in which you want to create the local repository using `cd` (change directory) command. This can also be done in windows.

To begin moving to your working directory use the cd command if you haven't clicked `Git Bash Here` in windows. For Mac and Linux operating systems, you may follow this until you reach your desired directory. 

Once you are in your desired directory, you may create the project directory by using mkdir command and get inside the project directory.

- `$ cd /d` - *(To move to your desired directory. Letter “d” is the drive name)*
- `$ mkdir new_project` - *(Create a new directory called new_project)*
- `$ cd new_project` - *(Move into the new_project directory)*

```bash
$ cd /d
$ mkdir new_project
$ cd new_project
```

To initialize a git repository in the root of the folder, run the `$ git init` command:

```bash
$ git init                     
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:

hint:     git config --global init.defaultBranch <name>

hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:

hint:     git branch -m <name>
Initialized empty Git repository in D:/new_project/.git/
```

Once you run the `$ git init` command, you get some hints and a command at the end showing that the git repository is initialized in your particular directory.

</br>

## Step 2: Add new files to the repository

You can create new files using your desired text editor or via `touch` command.

```bash
$ touch README.md
$ ls
README.md
```

`README.md` is a markdown file that contains the details of your repository or project.
The ls command shows the lists of files in the current directory

The `$ git status` command gives you the current state of the project including all commits, stages and the files tracked by git.

```bash
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
    README.md

nothing added to commit but untracked files present (use "git add" to track)
```

 Here, the `$ git status` command says that you have created a file called `README.md` but it says it's untracked and you haven't added it to a branch to be tracked. It won't be added to the git branch and get tracked unless you use the  `$ git add` command.

</br>

#### An interlude: The staging environment, the commit and you.

Most of the users get confused when they first learn the git concepts of staging environment and how it relates to a commit.

A commit is a record of when and what you did in the last state or change in the project. 
For example, if you add a file or modify a file in your repository you tell git to put those changes into a commit.

The staging environment tells which changed file to push in a commit. As seen in `step 2`, creating a file doesn’t do anything to a commit even when we know that a file has been created.

To add a file to a commit,  first, you need to add it to the staging environment.

- `$ git add <file name>` which will be done in *step 3*

*Note: The staging environment, also called `staging` is the preferred term but it is also referred to as `indexing`.*

</br>

## Step 3: Add a file to the staging environment

Add a file to the staging environment by using the `$ git add <filename with extension>` command.

If you see the git status the file has not been committed yet but the file has been staged for now.

```bash
$ git add README.md
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
    new file:   README.md
```

</br>

## Step 4: Create a commit

Run a command `$ git commit -m <Your commit message>` to create a commit from your staged file.

```bash
$ git commit -m "First Commit"
[master (root-commit) 09390cb] First Commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
```

The message at the end of the command should be something related to the commit contained, it can be a new feature, bug fixes or typos. Don’t put a message like `“ashajsdhgf”` or `“updates”`. This is because other programmers going through your project won't be understanding what changes you made in the commit. Commit lives forever in the repository and if you leave a meaningful commit message it will help other programmers to understand easily or it can be you in future who want to figure out why this change was made years later.

</br>

## Step 5: Create new branch

Branches allow you to develop features, fix bugs, or safely experiment with new ideas in a contained area of your repository. The Master branch is the first branch made when you initialize a Git repository. All repositories must have a master branch.

If you want to add new features on a branch without combining the new codes with previous versions or without combining codes with the master branch to prevent errors you may create new branches. Git branch comes in handy in these situations where you will be working on new features in a separate branch without making changes to the main branch.

Branch allows you to move back and forth between `states` of your project. For example, if you want to develop a website about a restaurant that becomes the main branch. If you want to develop a menu bar, you can create a branch name menu where you will develop a menu on the menu branch. When you finish developing it you can merge it to the main branch. When you create a branch git keeps track of which commit you `branched` off of, it maintains a history of what has happened over time.

To create a new branch use checkout command `$ git checkout -b <name of new branch>`
This command will automatically create a branch and check you out to that branch, meaning, git will move you to that branch, off from the primary or main branch.

```bash
$ git checkout -b menu
Switched to a new branch 'menu'
```

Use the `$ git branch` command to see your branch details.

```bash
$ git branch
  master
  * menu
```

The branch name with an asterisk indicates which branch you are currently at the moment.

*Note: By default, every git repository’s first branch is the master branch and is named as the `main` branch primary branch in a project.*

</br>

## Step 6: Create a new repository on GitHub

If you only want to keep track of your project in your local environment, you don’t need to use GitHub. But if you would like to work in a team, you can use GitHub to collaboratively modify the project code.

First, `Login` to [GitHub](https://github.com) and you will see your dashboard similar to this.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/2_github_dashboard.png" alt="GitHub Dashboard" />
 </a>
</p>

To create a [new repository](https://github.com/new) on your GitHub, go to the `Repositories` tab in your dashboard and click on `New` (green button)

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/3_github_repositories.png" alt="GitHub Repositories" />
 </a>
</p>

After clicking on the `New` button, GitHub will ask you to provide the `name` of the repository and give a brief description about it.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/4_create_repository.png" alt="Create Repository" />
 </a>
</p>

When you are done filling out the information click on the `Create repository` button.

Then, GitHub will ask you to create the repository from scratch or to add a repository locally. In this case, we have already created a new local repository so we will follow the “... or push an existing repository from the command line” 

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/5_repository_created.png" alt="Repository Created" />
 </a>
</p>

```bash
$ git remote add origin https://github.com/PemaRekdenDorjee/my_new_demo_repo.git
$ git branch -M main
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 239 bytes | 79.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/PemaRekdenDorjee/my_new_demo_repo.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

Once you get your own repository link, you can paste it in your bash and add origin using `$ git remote add origin <your repo link>`  command. You need to specify the branch you are pushing to by using the `$ git branch -M main` command.

Finally, you push your commit by using  `$ git push -u origin main`. This command will push the local repository to Github

*Note: 
Repository Link should be yours when you add origin in bash
Refresh your GitHub page you will see your local repository pushed successfully* 

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/6_first_commit.png" alt="First Commit" />
 </a>
</p>

</br>

## Step 7: Push a branch to GitHub

Now we will push the local branch which we have created to the GitHub repository.
If your branch is approved by the repository owner (In this case you are the owner so you can approve yourself), s/he will merge it to the main branch.

To push changes onto a new branch on GitHub
Run this command: `$ git push origin <your branch name>`

```bash
$ git push orgin menu
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0

remote: Create a pull request for 'menu' on GitHub by visiting:
remote: https://github.com/PemaRekdenDorjee/my_new_demo_repo/pull/menu

To https://github.com/PemaRekdenDorjee/my_new_demo_repo
 * [new branch]      menu -> menu
```

You can see now that two branches are pushed to the GitHub repository from our local repository.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/7_two_branches.png" alt="Two Branches" />
 </a>
</p>

Note: If this is your first time using GitHub locally then it might prompt you to log in to GitHub username and password.

</br>

## Step 8: Create a pull request (PR)

Pull request is a way to notify the repository owner that you need to make some changes in their primary branch.

For example, we will make some changes in our menu branch and pull request in the main branch in our repository to get merge. (Since this is on our repository same working principle is applied in other repositories).

You can see here that the `README.md` file has been modified via text editor and is committed to the menu branch.

```bash
$ git branch
  main
* menu
$ git add README.md
$ git status
On branch menu
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
$ git commit -m "added information in readme file"
[menu 2f693f4] added information in readme file
 1 file changed, 1 insertion(+)
```

Again push the menu branch from the local repo to GitHub.

```bash
$ git push orgin menu
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 320 bytes | 106.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/PemaRekdenDorjee/my_new_demo_repo
   15890c2..2f693f4  menu -> menu
```

You can see that the GitHub menu branch is updated now.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/8_branch_update.png" alt="Branch Updated" />
 </a>
</p>

Now we will pull the request and merge it to the main branch.
Click on the `pull request` tab and click on `compare and pull request`.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/10_pull_request.png" alt="Pull Request" />
 </a>
</p>

Now fill up the information in the comment section and assign yourself (In a team project you will assign others too).
Labels as documentation (since we are updating the readme file which is serving as a document for what the project is about).
For the reviewer leave blank (In a team you will assign a reviewer to review your changes).
Click on `create pull request`.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/9_open_pull_request.png" alt="Pull Request" />
 </a>
</p>

</br>

## Step 9: Merge a Pull Request

Now click on `merge pull request`. This will merge the changes into the primary branch

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/11_open_pull_request.png" alt="Open Pull Request" />
 </a>
</p>

You will see this message after successfully merging to the primary branch.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/12_merge_pull_request.png" alt="Merge Pull Request" />
 </a>
</p>

Click on the `commit` tab where you can see the hash code of the commit. *Hash code* is a unique identifier of that specific commit. It is useful to refer to specific commits and when undoing changes(use the `$ git revert <hash code>` command to backtrack).

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/13_pull_request_merged.png" alt="Merged Pull Request" />
 </a>
</p>

</br>

## Step 10: Get GitHub changes to your local machine

***(We haven't done any changes in the GitHub repository in this case. For instance if you are working in a team the repository get updates on Github so you need to get changes to your local machine )***

For this case we will directly edit the `main` branch `README.md` file and add a new line and merge it. You can easily edit the file in the GitHub interface by clicking on the `pencil icon`.

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/14_edit.png" alt="Edit" />
 </a>
</p>

Files have been updated by committing from the GitHub interface (Not recommended but you can commit from here too. Use Visual Code Editor which has a built-in git version control to make changes from your local machine ).

<p align="center">
 <a target="_blank" href="https://github.com/btdevcommunity/documentation/blob/main/git-github-tutorial.md">
  <img src="https://github.com/btdevcommunity/documentation/blob/main/assets/git-github-tutorial/15_new_line_added.png" alt="Edited" />
 </a>
</p>

Now we will fetch these changes to our local repository.
Run this command: `$ git pull origin main`

```bash
$ git pull orgin main
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), 1.33 KiB | 3.00 KiB/s, done.
From https://github.com/PemaRekdenDorjee/my_new_demo_repo
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> orgin/main
Updating 15890c2..8e2971a
Fast-forward
 README.md | 3 +++
 1 file changed, 3 insertions(+)
```

Now check the `$ git log` command to see all the changes committed. 

```bash
Date:   Wed Feb 9 01:28:13 2022 +0600

    Update README.md

    added new line of information for the tutorial

commit ac788fc90b22370c1926c5fa2281cf889927faf1
Merge: 15890c2 2f693f4
Author: Pema Dorji Sherpa <pemarekdendorjee@gmail.com>
Date:   Wed Feb 9 01:06:47 2022 +0600

    Merge pull request #1 from PemaRekdenDorjee/menu

    added information in readme file

commit 2f693f4516df322c01d18abd48252f7566188fff (orgin/menu, menu)
Author: Pema Dorji Sherpa <pemarekdendorjee@gmail.com>
Date:   Wed Feb 9 00:39:41 2022 +0600

    added information in readme file

commit 15890c2e912e76748b9245db45fa23a2e2cf4cc3 (origin/main, orgin/master)
Author: Pema Dorji Sherpa <pemarekdendorjee@gmail.com>
Date:   Tue Feb 8 22:10:02 2022 +0600

    First Commit
```

Note: It is recommended to delete the branch after merging into the primary branch as it may get confusing with multiple branches..

Additional command

- Switch branch: `$ git checkout <name of branch>`
- Delete branch: `$ get branch -d <name of branch>`

### You sucessfully completed learning basic Git

Additional Resources

- [Git Cheat Sheets - GitHub Training](https://training.github.com/)
- [Learn Git Branching](https://learngitbranching.js.org/)
- [GitHub - arslanbilal : git-cheat-sheet](https://github.com/arslanbilal/git-cheat-sheet)
