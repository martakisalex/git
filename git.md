# Git

This markdown explains how to use Git and how to use it on remote repository platforms, like GitHub.

# Table of Contents
* [Git and GitHub Introduction](#git-and-github-introduction)
* [Git Getting Started](#git-getting-started)
## References
* [Git Tutorial](https://www.w3schools.com/git/default.asp)
* [How to Write Good Commit Messages: A Practical Git Guide](https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/ "How to Write Good Commit Messages: A Practical Git Guide")
* [Changing a commit message](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message "Changing a commit message")
* [Git and GitHub for Beginners Tutorial](https://youtu.be/tRZGeaHPoaw "Git and GitHub for Beginners Tutorial")
* [Git commit message](https://github.com/joelparkerhenderson/git-commit-message/)
# Git and GitHub Introduction

## What is git?

Git is a popular version control system. It was created by Linus Torvalds in 2005, and has been maintained by Junio Hamano since then.

It is used for:
* Tracking code changes
* Tracking who made changes
* Coding collaboration

## What does Git do?
* Manage projects with **Repositories**
* **Clone** a project to work on a local copy
* Control and track changes with **Staging** and **Committing**
* **Branch** and **Merge** to allow for work on different parts and versions of a project
* **Pull** the latest version of the project to a local copy
* **Push** local updates to the main project

## Working with Git
* Initialize Git on a folder, making it a **Repository**
* Git now creates a hidden folder to keep track of change in that folder
* When a file is changed, added or deleted, it is considered **modified**
* You select the modified files you want to **Stage**
* The **Staged** files are **Committed**, which prompts Git to store a **permanent** snapshot of the files
* Git allows you to see the full history of every commit
* You can revert back to any previous commit
* Git does not store a separate copy of every file in every commit, but keeps track of changes made in each commit!

## Why Git?
* Over 70% of developers use Git
* Developers can work together from anywhere in the world
* Developers can see the full history of the project
* Developers can revert to earlier versions of a project

## What is GitHub?
* Git is not the same as GitHub
* GitHub makes tools that use Git
* GitHub is the largest host of source code in the world, and has been owned by Microsoft since 2018
# Git Getting Started

## Git Install

You can download Git for free from the following website: https://www.git-scm.com/

## Using Git with Command Line

To start using Git, we are first going to open up our Command shell.

For Windows, you can use Git bash, which comes included in Git for Windows. For Mac and Linux you can use the built-in terminal.

The first thing we need to do, is to check if Git is properly installed:

>$ git --version

If Git is installed, it should show something along the lines of git version X.Y

## Configure git

Now let Git know who you are. This is important for version control systems, as each Git commit uses this information:

>$ git config --global user.name "johndoe-test"
> 
>$ git config --global user.email "johndoe@email.com"

Change the user name and e-mail address to your own. You will probably also want to use this when registering to GitHub later on.

*Note: Use <font face="Courier" style="color:coral">global</font> to set the username and e-mail for every repository on your computer. If you want to set the username/e-mail for just the current repo, you can remove <font face="Courier" style="color:coral">global</font>*

## Creating Git Folder

Create a new folder for your project:

>$ mkdir myproject
> 
>$ cd myproject

<font face="Courier" style="color:coral">mkdir</font> makes a new directory

<font face="Courier" style="color:coral">cd</font> changes the current working directory

Now that you are in the correct directory, you can start by initializing Git

*Note: If you already have a folder/directory you would like to use for Git, navigate to it in command line, or open it in your file explorer, right-click and select "Git Bash here"*

## Initialize Git

Once you have navigated to the correct folder, you can initialize Git on that folder:

>$ git init
>
> Initialized empty Git repository in /Users/user/myproject/.git/

*Note: Git now knows that it should watch the folder you initiated it on. 
Git creates a hidden folder to keep track of changes.*
# Git New Files
## Git Adding New Files

You just created your first local Git repo. But it is empty.

Add or create some file such as <font face="courier" style="color:coral">git.md</font> in the directory

Go back to the terminal and list the files in the current working directory:
>$ ls

You will see that the file(s) you created are now there

Then we check the Git states and see if it is part of your repo: 

>$ git status

Git is **aware** of the files, but has not **added** it to your repository

Files in your Git repository folder can be in one of 2 states:

* Tracked - files that Git knows about and are added to the repository

* Untracked - files that are in your working directory, but not added to the repository

When you first add files to an empty repository, they are all untracked. To get Git to track them, you need to stage them, or add them to the staging environment.

# Git Staging Environment
## Git Staging Environment

One of the core functions of Git is the concepts of the Staging Environment, and the Commit.

As you are working, you may be adding, editing and removing files. But whenever you hit a milestone or finish a part of the work, you should add the files to a Staging Environment.

**Staged** files are files that are ready to be **committed** to the repository you are working on. You will learn more about <font face="courier" style="color:coral">commit</font> shortly.

Say we are done working with <font face="courier" style="color:coral">git.md</font>. We can add it to the Staging Environment:

>$ git add git.md

The file should be Staged. Let's check the status::

>$ git status

Now the file has been added to the Staging Environment.

## Git Add More than One File

You can also stage more than one file at a time. Let's add 2 more files to our working folder. Use the text editor again.

A <font face="courier" style="color:coral">README.md</font> file that describes the repository (recommended for all repositories):

>$ cat > README.md

Now add all files in the current directory to the Staging Environment:

>$ git add --all

Using <font face="courier" style="color:coral">--all</font> instead of individual filenames will stage all changes (new, modified, and deleted) files.

Now all 3 files are added to the Staging Environment, and we are ready to do our first <font face="courier" style="color:coral">commit</font>.

**Note:** The shorthand command for <font face="courier" style="color:coral">git add --all</font> is <font face="courier" style="color:coral">git add -A</font>