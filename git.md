# Git

This markdown explains how to use Git and how to use it on remote repository platforms, like GitHub.

# Table of Contents
* [Git and GitHub Introduction](#git-and-github-introduction)
* [Git Getting Started](#git-getting-started)
* [Git New Files](#git-new-files)
* [Git Staging Environment](#git-staging-environment)
* [Git Commit](#git-commit)
* [Git Help](#git-help)
* [Git Branch](#git-branch)
* [Git Branch Merge](#git-branch-merge)

## References
* [Git Tutorial](https://www.w3schools.com/git/default.asp)
* [How to Write Good Commit Messages: A Practical Git Guide](https://www.freecodecamp.org/news/writing-good-commit-messages-a-practical-guide/ "How to Write Good Commit Messages: A Practical Git Guide")
* [Changing a commit message](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/changing-a-commit-message "Changing a commit message")
* [Git and GitHub for Beginners Tutorial](https://youtu.be/tRZGeaHPoaw "Git and GitHub for Beginners Tutorial")
* [Git commit message](https://github.com/joelparkerhenderson/git-commit-message/)
## Repo
> https://github.com/Sikatram/git/

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

  Note: Git now knows that it should watch the folder you initiated it on. 
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

# Git Commit
## Git Commit

Since we have finished our work, we are ready move from <font face="courier" style="color:coral">stage</font> to <font face="courier" style="color:coral">commit</font> for our repo.

Adding commits keep track of our progress and changes as we work. Git considers each <font face="courier" style="color:coral">commit</font> change point or "save point". It is a point in the project you can go back to if you find a bug, or want to make a change.

When we <font face="courier" style="color:coral">commit</font>, we should **always** include a **message**.

By adding clear messages to each <font face="courier" style="color:coral">commit</font>, it is easy for yourself (and others) to see what has changed and when.

> git commit -m "First release of git tutorial"

## Git Commit without Stage

Sometimes, when you make small changes, using the staging environment seems like a waste of time. It is possible to commit changes directly, skipping the staging environment. The <font face="courier" style="color:coral">-a</font> option will automatically stage every changed, already tracked file.

Let's add a small update to git.md:

And check the status of our repository. But this time, we will use the --short option to see the changes in a more compact way:

> git status --short

**Note:** Short status flags are:

* ?? - Untracked files
* A - Files added to stage
* M - Modified files
* D - Deleted files

We see the file we expected is modified. So let's commit it directly:

>$ git commit -a -m "Updated git.md with a new tutorial section"

<mark style="background-color:#FFCCCB">
<b>Warning:</b> Skipping the Staging Environment is not generally recommended.
Skipping the stage step can sometimes make you include unwanted changes.
</mark>

## Git Commit Log

To view the history of commits for a repository, you can use the <font face="courier" style="color:coral">log</font> command:

>$ git log

# Git Help
## Git Help

If you are having trouble remembering commands or options for commands, you can use Git <font face="courier" style="color:coral">help</font>.

There are a couple of different ways you can use the <font face="courier" style="color:coral">help</font> command in command line:

* <font face="courier" style="color:coral">git command -help</font> -  See all the available options for the specific command
* <font face="courier" style="color:coral">git help --all</font> -  See all possible commands

Let's go over the different commands.

## Git -help See Options for a Specific Command

Any time you need some help remembering the specific option for a command, you can use <font face="courier" style="color:coral">git command -help</font>:

> $git commit -help

**Note:** You can also use --help instead of -help to open the relevant Git manual page

## Git help --all See All Possible Commands

To list all possible commands, use the <font face="courier" style="color:coral">help --all</font> command:

<mark style="background-color:#FFCCCB">
<b>Warning:</b> This will display a very long list of commands
</mark>

>$ git help --all

**Note:** If you find yourself stuck in the list view, <font face="courier" style="color:coral">SHIFT + G</font> to jump the end of the list, then <font face="courier" style="color:coral">q</font> to exit the view.

# Git Branch

## Working with Git Branches

In Git, a <font face="courier" style="color:coral">branch</font> is a new/separate version of the main repository.

Let's say you have a large project, and you need to update the design on it.

How would that work without and with Git:

Without Git:

* Make copies of all the relevant files to avoid impacting the live version
* Start working with the design and find that code depend on code in other files, that also need to be changed!
* Make copies of the dependant files as well. Making sure that every file dependency references the correct file name
* EMERGENCY! There is an unrelated error somewhere else in the project that needs to be fixed ASAP!
* Save all your files, making a note of the names of the copies you were working on
* Work on the unrelated error and update the code to fix it
* Go back to the design, and finish the work there
* Copy the code or rename the files, so the updated design is on the live version
* (2 weeks later, you realize that the unrelated error was not fixed in the new design version because you copied the files before the fix)

With Git:

* With a new branch called new-design, edit the code directly without impacting the main branch
* EMERGENCY! There is an unrelated error somewhere else in the project that needs to be fixed ASAP!
* Create a new branch from the main project called small-error-fix
* Fix the unrelated error and merge the small-error-fix branch with the main branch
* You go back to the new-design branch, and finish the work there
* Merge the new-design branch with main (getting alerted to the small error fix that you were missing)

Branches allow you to work on different parts of a project without impacting the main branch.

When the work is complete, a branch can be merged with the main project.

You can even switch between branches and work on different projects without them interfering with each other.

Branching in Git is very lightweight and fast!

## New Git Branch

Let's add some content to our <font face="courier" style="color:coral">git.md</font> page.

We are working in our local repository, and we do not want to disturb or possibly wreck the main project.

So we create a new <font face="courier" style="color:coral">branch</font>:

>$ git branch git-branch-tutorial

Now we created a new <font face="courier" style="color:coral">branch</font> called "<font face="courier" style="color:coral">git-branch-tutorial</font>"

Let's confirm that we have created a new <font face="courier" style="color:coral">branch</font>:

>$ git branch

We can see the new branch with the name "git-branch-tutorial", but the <font face="courier" style="color:coral">*</font> beside <font face="courier" style="color:coral">master</font> specifies that we are currently on that <font face="courier" style="color:coral">branch</font>.

<font face="courier" style="color:coral">checkout</font> is the command used to check out a <font face="courier" style="color:coral">branch</font>. Moving us **from** the current <font face="courier" style="color:coral">branch</font>, **to** the one specified at the end of the command:

>$ git checkout git-branch-tutorial

Now we have moved our current workspace from the master branch, to the new <font face="courier" style="color:coral">branch</font>

Open your favourite editor and make some changes.

We have made changes to a file and added a new file in the working directory (same directory as the <font face="courier" style="color:coral">main branch</font>).

Now check the status of the current <font face="courier" style="color:coral">branch</font>:

>$ git status

So let's go through what happens here:

* There are changes to our git.md, but the file is not staged for <font face="courier" style="color:coral">commit</font>

So we need to add the file to the Staging Environment for this branch:

>$ git add --all

Using <font face="courier" style="color:coral">--all</font> instead of individual filenames will **Stage** all changed (new, modified, and deleted) files.

Check the <font face="courier" style="color:coral">status</font> of the <font face="courier" style="color:coral">branch</font>:

>$ git status

We are happy with our changes. So we will commit them to the <font face="courier" style="color:coral">branch</font>:

>$ git commit -m "Added branch tutorial to git.md"

Now we have a new <font face="courier" style="color:coral">branch</font>, that is different from the master <font face="courier" style="color:coral">branch</font>.

**Note:** Using the <font face="courier" style="color:coral">-b</font> option on <font face="courier" style="color:coral">checkout</font> will create a new branch, and move to it, if it does not exist

## Switching Between Branches

Now let's see just how quick and easy it is to work with different branches, and how well it works.

We are currently on the branch <font face="courier" style="color:coral">git-branch-tutorial</font>. We added content to this branch, so let's list the files in the current directory:

>$ ls

If we open the git.md file, we can see the code has been altered. All is as it should be.

Now, let's see what happens when we change branch to <font face="courier" style="color:coral">master</font>

>$ git checkout master

The updated <font face="courier" style="color:coral">git.md</font> is not a part of this branch. List the files in the current directory again:

If we open the md file, we can see the text reverted to what it was before the alteration.

See how easy it is to work with branches? And how this allows you to work on different things?

## Emergency Branch

Now imagine that we are not yet done with git-branch-tutorial, but we need to fix an error on master.

I don't want to mess with master directly, and I do not want to mess with git-branch-tutorial, since it is not done yet.

So we create a new branch to deal with the emergency:

>$ git checkout -b emergency-fix

Now we have created a new branch from master, and changed to it. We can safely fix the error without disturbing the other branches.

Let's fix our imaginary error in the README.md:

We have made changes in this file, and we need to get those changes to the master branch.

Check the status:

>$ git status

stage the file, and commit:

>$ git add README.md
>
>$ git commit -m "updated README.md with emergency fix"

Now we have a fix ready for master, and we need to merge the two branches.

# Git Branch Merge

## Merge Branches

We have the emergency fix ready, and so let's merge the master and emergency-fix branches.

First, we need to change to the master branch:

>$ git checkout master

Now we merge the current branch (master) with emergency-fix:

>$ git merge emergency-fix

Since the emergency-fix branch came directly from master, and no other changes had been made to master while we were working, Git sees this as a continuation of master. So it can "Fast-forward", just pointing both master and emergency-fix to the same commit.

As master and emergency-fix are essentially the same now, we can delete emergency-fix, as it is no longer needed:

>$ git branch -d emergency-fix

## Merge Conflict

Now we can move over to git-branch-tutorial and keep working by adding a new section of the tutorial.

>$ git checkout git-branch-tutorial

Now, we are done with our work here and can stage and commit for this branch:

>$ git add --all
>
>$ git commit -m "added new tutorial section"

We see that git.md has been changed in both branches. Now we are ready to merge git-branch-tutorial into master. But what will happen to the changes we recently made in master?

>$ git checkout master
>
>$ merge git-branch-tutorial

The merge failed, as there is conflict between the versions for git.md. Let us check the status:

>$ git status

This confirms there is a conflict in index.html, but the image files are ready and staged to be committed.

So we need to fix that conflict. Open the file in our editor:

We can see the differences between the versions and edit it like we want:

Now we can stage git.md and check the status:

>$ git add git.md
>
>$ git status

The conflict has been fixed, and we can use commit to conclude the merge:

>$ git commit -m "Merge with git-branch-tutorial after fixing conflicts"

And delete the git-branch-tutorial branch:

>$ git brnach -d git-branch-tutorial

Now you have a better understanding of how branches and merging works. Time to start working with a remote repository!

# GitHub Getting Started

## GitHub Account

Go to [GitHub](https://github.com/) and sign up for an account.

***Note:** Remember to use the same e-mail address you used in the Git config.*


## Create a Repository on GitHub

Now that you have made a GitHub account, sign in, and create a new Repo and fill in the relevant details.

We will go over the different options and what they mean later. But for now, choose Public (if you want the repo to be viewable for anyone) or Private (if you want to choose who should be able to view the repo). Either way, you will be able to choose who can **contribute** to the repo.

Then click "Create repository".

## Push Local Repository to GitHub

Since we have already set up a local Git repo, we are going to <font face="courier" style="color:coral">push</font> that to GitHub.

Copy the URL, or click the clipboard marked in the image above.

Now paste it the following command:

> $ git remote add origin https://github.com/[username]/[repo-name]

<font face="courier" style="color:coral">git remote add origin URL</font> specifies that you are adding a remote repository, with the specified <font face="courier" style="color:coral">URL</font>, as an <font face="courier" style="color:coral">origin</font> to your local Git repo.

Now we are going to push our master branch to the origin url, and set it as the default remote branch:

> $ git push --set-upstream origin master

*Note: Since this is the first time you are connecting to GitHub, you will get some kind of notification you to authenticate this connection.*

Now, go back into GitHub and see that the repository has been updated.


# Git GitHub Edit Code

In addition to being a host for Git content, GitHub has a very good code editor.

Let's try to edit the README.md file in GitHub. Just click the edit button.

Add some changes to the code, and then <font face="courier" style="color:coral">commit</font> the changes. For now, we will "Commit directly to the master branch".

Remember to add a description for the <font face="courier" style="color:coral">commit</font>.

That is how you edit code directly in GitHub.

# Git Pull from GitHub

## Pulling to Keep up-to-date with Changes

When working as a team on a project, it is important that everyone stays up to date.

Any time you start working on a project, you should get the most recent changes to your local copy.

With Git, you can do that with <font face="courier" style="color:coral">pull</font>.

<font face="courier" style="color:coral">pull</font> is a combination of 2 different commands:

* <font face="courier" style="color:coral">fetch</font>
* <font face="courier" style="color:coral">merge</font>

Let's take a closer look into how <font face="courier" style="color:coral">fetch</font>, <font face="courier" style="color:coral">merge</font>, and <font face="courier" style="color:coral">pull</font> works.

## Git Fetch

<font face="courier" style="color:coral">fetch</font> gets all the change history of a tracked branch/repo.

So, on your local Git, <font face="courier" style="color:coral">fetch</font> updates to see what has changed on GitHub:

> git fetch origin

Now that we have the recent <font face="courier" style="color:coral">changes</font>, we can check our <font face="courier" style="color:coral">status</font>:

> git status

We are behind the <font face="courier" style="color:coral">origin/master</font> by 1 <font face="courier" style="color:coral">commit</font>. That should be the updated <font face="courier" style="color:coral">README.md</font>, but lets double check by viewing the <font face="courier" style="color:coral">log</font>:

> git log origin/master

That looks as expected, but we can also verify by showing the differences between our local <font face="courier" style="color:coral">master</font> and <font face="courier" style="color:coral">origin/master</font>:

> git diff origin/master

That looks precisely as expected! Now we can safely <font face="courier" style="color:coral">merge</font>.

## Git Merge

<font face="courier" style="color:coral">merge</font> combines the current branch, with a specified branch.

We have confirmed that the updates are as expected, and we can merge our current branch (<font face="courier" style="color:coral">master</font>) with <font face="courier" style="color:coral">origin/master</font>:

> git merge origin/master

Check our <font face="courier" style="color:coral">status</font> again to confirmwe are up to date:

> git status

There! Your local git is up to date!

## Git Pull

But what if you just want to update your local repository, without going through all those steps?

<font face="courier" style="color:coral">pull</font> is a combination of <font face="courier" style="color:coral">fetch</font> and <font face="courier" style="color:coral">merge</font>. It is used to pull all changes from a remote repository into the branch you are working on.

Make another change to the Readme.md file on GitHub.

Use <font face="courier" style="color:coral">pull</font> to update our local Git:

> git pull origin

That is how you keep your local Git up to date from a remote repository. In the next chapter, we will look closer at how <font face="courier" style="color:coral">push</font> works on GitHub.

# Git Push to GitHub

## Push Changes to GitHub

Let's try making some changes to our local git and pushing them to GitHub.

Edit the README.md

Commit the changes:
> git commit -a -m "Update README.md."

And check the status:
> git status

Now push our changes to our remote origin:
> git push origin

Go to GitHub, and confirm that the repository has a new commit.

# Git GitHub Branch

## [Create a New Branch on GitHub](https://www.w3schools.com/git/git_remote_branch.asp?remote=github)

On GitHub, access your respository and click the "master" branch button.

There you can create a new Branch. Type in a descriptive name, and click Create branch.

Let's call the branch, "<font face="courier" style="color:coral">update-git</font>"

The <font face="courier" style="color:coral">branch</font> should now be created and active. You can confirm which branch you are working on by looking at the branch button. See that it now says "update-git" instead of "main"?

Start working on an existing file in this branch. Click the "<font face="courier" style="color:coral">git.md</font>" file and start editing.

After you have finished editing the file, you can click the "Preview changes" tab to see the changes you made highlighted.

If you are happy with the change, add a comment that explains what you did, and click Commit changes.

You now have a new <font face="courier" style="color:coral">branch</font> on GitHub, updated with some changes!

# Git Pull Branch from GitHub

## Pulling a Branch from GitHub

Now continue working on our new <font face="courier" style="color:coral">branch</font> in our local Git.

Lets <font face="courier" style="color:coral">pull</font> from our GitHub repository again so that our code is up-to-date:

>git pull

Now our main <font face="courier" style="color:coral">branch</font> is up-to-date. And we can see that there is a new <font face="courier" style="color:coral">branch</font> available on GitHub.

Do a quick <font face="courier" style="color:coral">status</font>:

>git status

And confirm which branches we have, and where we are working at the moment:

>git branch

So, we do not have the new <font face="courier" style="color:coral">branch</font> on our local Git. But we know it is available on GitHub. So we can use the <font face="courier" style="color:coral">-a</font> option to see all local and remote branches:

>git branch -a

*Note: <font face="courier" style="color:coral">branch -r</font> is for remote brances only.*

We see that the branch <font face="courier" style="color:coral">readme</font> is available remotely, but not on our local git. Lets check it out:

>git checkout readme

And check if it is all up to date:

>git pull

Which branches fo we have now, and where are we working from?

>git branch

Now, open your favourite editor and confirm that the changes from the GitHub branch carried over.

That is how you pull a GitHub branch to your local Git.

# Git Push Branch to GitHub

## Push a Branch to GitHub

Let's try to create a new local branch, and push that to GitHub.

Start by creating a branch, like we did earlier:

>git checkout -b update-readme

And we make some changes to the README.md file. Just add a new line.

So now we check the <font face="courier" style="color:coral">status</font> of the current branch.

>git status

We see that <font face="courier" style="color:coral">README.md</font> is modified but not added to the Staging Environment:

>git add README.md

Check the <font face="courier" style="color:coral">status</font> of the branch:

>git status

We are happy with our changes. So we will <font face="courier" style="color:coral">commit</font> them to the <font face="courier" style="color:coral">branch</font>:

>git commit -m "Update readme for GitHub Branches"

Now <font face="courier" style="color:coral">push</font> the <font face="courier" style="color:coral">branch</font> from our local Git repository, to GitHub, where everyone can see the changes:

>git push origin update-readme

Go to GitHub, and confirm that the repository has a new <font face="courier" style="color:coral">branch</font>.

In GitHub, we can now see the changes and <font face="courier" style="color:coral">merge</font> them into the master <font face="courier" style="color:coral">branch</font> if we approve it.

If you click the "Compare & pull request", you can go through the changes made and new files added.

Note: This comparison shows both the changes from <font face="courier" style="color:coral">update-readme</font> and <font face="courier" style="color:coral">update-git</font> because we created the new branch FROM <font face="courier" style="color:coral">update-git</font>.

If the changes look good, you can go forward, creating a <font face="courier" style="color:coral">pull request</font>.

A pull request is how you propose changes. You can ask some to review your changes or pull your contribution and merge it into their branch.

Since this is your own repository, you can  <font face="courier" style="color:coral">merge</font> your pull request yourself:

The pull request will record the changes, which means you can go through them later to figure out the changes made.

To keep the repo from getting overly complicated, you can delete the now unused branch by clicking "Delete branch".

An after you confirm that the changes from the previous branch were included, delete that as well.
