---
layout: post
title: "Git Tutorial"
description: "This tutorial will help you understand how git works and how to use git to submit your commit on Github."
tags: git GitHub tutorial
comments: true
---

*Note: This tutorial is about using Git in bash/cmd, which we highly recommend, as it’s cleaner. Github is a totally different thing, it is the web interface or app.*

# How to install Git

First step is installing Git. Supposing you are on a Debian-based distribution, this will do:

```bash
$ sudo apt-get install git
```

For installing Git on a Mac OS system, you can use the homebrew package manager as follows:
```bash
$ brew install git
```

# Getting Started with Addy

First of all, you have to fork the repository you are going to contribute to. This will basically give you a clone of the repository to your own repository. You can do this by opening the specific repository of `addy-org` and then clicking `Fork` in the upper right corner.

# Cloning repository into your local system

Now you should clone the repository to your local machine so that you can have access to all the code locally and start fixing issues! To do this, you can use the following procedure to clone the specific repository into your local system.

- Open you terminal/ cmd/ git-bash whatever you would use to run the git commands.
- Navigate to the folder where you want to save your code. *(Use `cd, ls, etc.` terminal commands)*
- Now type

```bash
$ git clone -o upstream <repository_url>
```
>*where `<repository_url>` is the whole url of the git repository you want to clone*<br/>
*`upstream` is just a name we used for simplicity. You can name it however you want.*

**For Example**,

- to clone ***addy-org/Addy*** project,

```bash
$ git clone -o upstream https://github.com/addy-org/Addy
```

- to clone ***addy-org/Addy-Android*** project,

```bash
$ git clone -o upstream https://github.com/addy-org/Addy-Android
```

Congratulations! now you have all your code on your local machine!

# Getting to work

Before starting to edit the code, make sure to read & check the following to avoid problems later on.

## Remote
First let’s talk about remotes. To communicate with the outside world, git uses what are called remotes. These are repositories other than the one on your local disk which you can push your changes into (so that other people can see them) or pull from (so that you can get others changes). Now you should add a remote of your fork to your local machine so that you can pull and push your commits. This can be simply done by using the command:

```bash
$ git remote add myfork <your_fork_link>
```
> ***Note:*** *`myfork` is just a name we used for simplicity. You can name it however you want.*

## Status

The next thing you should know before getting down to work is how to check on the changes you’ve made to your project, and your current branch. The ability to check your current branch is also extremely important, as you’ll see in the next section. The command to check this information is:

```bash
$ git status
```

Before we move onto the next section, you need to know about a very important branch called master. Master is the default branch that git checkouts for you when you clone a repository. For the sake of avoiding major problems, we should never develop on our fork’s master branch. This is why we create new branches, which leads us to the next section.

# Creating a new branch

To start working on an issue, you first need to create a new branch where you will work. Do not change files when you are on your fork’s master branch. The reason why you should never develop on your master branch is because your fork’s master branch should always be synchronised with the main repository’s master branch, which is much more challenging if it has new commits on it. This is why we create our own branch:
```bash
$ git checkout -b branchname
```
> **Note:**<br />
- `checkout` will switch to the newly created branch.
- `-b` will create a new branch if the branch doesn’t already exist.

# Checking your work

After the issue is fixed and you have tested it (tests are very important! never submit a change that isn’t tested), you should check your progress. Type:

```bash
$ git status
```
It will give you an idea about what files are currently modified and which branch you’re developing on.
>**Tip:** <br />
If there’s something you don’t find, you can always use:
```bash
$ git grep "syntax"
```
This will search through the whole repository and show you the files that contain the syntax.

# Adding the files

First, make sure you’re on the correct branch and not developing on master! You can check your branch with:

```bash
$ git status
```

Now you can add your files/folders to the current commit:

```bash
$ git add <file/folder_name>
```

Do this until you have added all the files needed for your commit. You can also simple use
```bash
$ git add .
```
to add all the files at once.

# Committing the files

After adding the files, the next step is to commit them. You can see the [commit guidelines](../commit-guidelines/) to know how to write some good commits.

To commit the added files, type:
```bash
$ git commit
```
This will lead you to a text editor. Write you commit message there, you may read the [commit guidelines](../commit-guidelines/)
>Commits usually consists of two main parts.
- commit message
- commit description<br /><br />
>Example:<br /><br/>
>`Gemfile.lock: Update nokogiri version // Commit Message`<br /><br />
>```
// Commit Description
This upgrades nokogiri version to 1.8.1
and hence other dependencies are updated too
This was done due to a potential security
vulnerability stated by GitHub
```

Now that your message is written, you will have to save the file. Press escape to exit insert mode, and save the file (in Vim that is being done by pressing shift + Z twice).

# Pushing the commit

Before you push the commit, ensure that you are not developing on master again by running:

```bash
$ git status
```

Now you will need to push the commit to the fork. All you have to do is:

```bash
$ git push myfork
```

It will most likely ask for your login credentials from GitHub. Type them in, and your commit will be pushed online.

# Creating a Pull Request

Now you would like to get your commit into the actual master branch. Making your changes available to all future users of the project. For this, you will have to create a Pull Request. To do this, you will have to go on GitHub, on your fork page. You should change the branch to the one you have worked on and submitted the commit on. Now you can create a Pull Request by clicking the `New Pull Request` button in the pull request tab.

**Congratulations!** You have just created your first Pull Request! You are awesome!

>***Note:*** *If you see any error like `1 commit ahead of the master branch` you need to sync your local fork with the remote repository before sending a pull request.*

# Follow-up

Now after you have created the Pull Request, there are two possibilities:

- your PR will get accepted, and your commit will get merged into the master branch - sadly, this rarely happens on the first Pull Request

- your PR will be rejected. There are 2 cases when a PR is rejected:
  - Test fails
  - Reviewer wants something changed

It’s highly unlikely that your PR will be accepted on the first attempt - but don’t worry that’s just how it works.

Now if you need to modify your code, you can simply edit it again, add it and commit it using

```bash
$ git commit -a --amend
```

This will edit your last commit message. If your commit message was considered fine by our reviewers, you can simply send it again like this. If not, edit it and send it. Now you have successfully edited your last commit!

If you need to rebase, or want to edit an older commit from your branch, we have an amazing [tutorial that you can watch](https://asciinema.org/a/78683) to understand how it works.

# Rebasing

As people work on Addy new commits will be added. This will result in your local fork going out of sync with the remote repository. To sync your changes with the remote repository run the following commands in the desired branch:

```bash
$ git fetch upstream
$ git rebase upstream/master
```

>***Note:***<br/>
*This assumes that the remote upstream is the original  repository at addy-org, not your fork.*

This will fetch the commits from the remote repository and will merge it into the branch where you are currently working, and move all of the local commits that are ahead of the rebased branch to the top of the history on that branch.

# Force Push

After following these instructions when you try to push to remote you may get fast-forwarding error. If that is the case, then you will have to force push since you are attempting to rewrite the git commit history. To do that append the --force argument in the push command:
```bash
$ git push myfork --force
```

>**Warning:**<br/>
Never force-push on the master branch, or any branch not owned by you.

To verify whether you have rebased correctly, go to the web page of the branch in your fork. If it says your branch is n commits behind Addy:master (or whichever repo you are contributing to), then you haven’t correctly rebased yet. Otherwise, you’re good to go!

# Squashing your commits

It’s possible that you have more than one commit and you want them to be squashed into a single commit. You can take your series of commits and squash them down into a single commit with the interactive rebasing tool. To squash your commits run the following command:

```bash
$ git rebase -i master
```

An editor will be fired up with all the commits in your current branch (ignoring merge commits), which come after the given commit. Keep the first one as “pick” and on the second and subsequent commits with “squash”. After saving, another editor will be fired up with all the messages of commits which you want to squash. Clean up all the messages and add a new message to be displayed for the single commit.

# Reverting Commits

Sometimes it might happen that you have committed the wrong files and you want to revert the commit. Hence, in your local repo, to revert the file to the state before the previous commit run the following:

```bash
$ git reset --soft HEAD^
```
> `--soft` helps you retain the changes and reverts the commit, you can also use `--hard` which will also remove the changes you have done.

If you want to revert multiple commits execute the following:

```bash
$ git reset --soft HEAD~N
```
> Where `N` stands for the number of commits from the HEAD commit (latest commit) you want to reset.

**For Example:**
to reset last 3 commits, execute:
```bash
$ git reset --soft HEAD~3
```

# Useful Git commands

This section will briefly explain some other Git commands you will most likely use and will really make your work easier.

**`$ git config`**
>The `git config` command lets you configure your Git installation (or an individual repository) from the command line. This command can define everything from user info to preferences to the behavior of a repository.

**`$ git log`**
>The `git log` command displays committed snapshots. It lets you list the project history, filter it, and search for specific changes. While git status lets you inspect the working directory and the staging area, git log only operates on the committed history.

**`$ git push --force myfork`**
>While we normally use `git push myfork` to push your commit to your fork, after further editing and work on your commit, you will need to use the `--force` parameter to your push to automatically update your Pull Request.

**`$ git reset --hard`**
>Reset the staging area and the working directory to match the most recent commit. In addition to unstaging changes, the --hard flag tells Git to overwrite all changes in the working directory, too. Put another way: this obliterates all uncommitted changes, so make sure you really want to throw away your local developments before using it.

**`$ git clean`**
>The git clean command removes untracked files from your working directory. This is really more of a convenience command, since it’s trivial to see which files are untracked with git status and remove them manually. Like an ordinary rm command, git clean is not undoable, so make sure you really want to delete the untracked files before you run it.

**`$ git checkout <branch>`**
>The `git checkout` command is used to switch to another branch in the repository. Here <branch> is the name of the branch you want to switch to.

**`$ git rebase`**
>Rebasing is the process of moving a branch to a new base commit. From a content perspective, rebasing really is just moving a branch from one commit to another. But internally, Git accomplishes this by creating new commits and applying them to the specified base—it’s literally rewriting your project history. It’s very important to understand that, even though the branch looks the same, it’s composed of entirely new commits.

**`$ git rebase -i`**
>Running `git rebase` with the -i flag begins an interactive rebasing session. Instead of blindly moving all of the commits to the new base, interactive rebasing gives you the opportunity to alter individual commits in the process. This lets you clean up history by removing, splitting, and altering an existing series of commits. It’s like `git commit --amend` on steroids. Usage is `$ git rebase -i <base>`. Rebase the current branch onto <base>, but use an interactive rebasing session. This opens an editor where you can enter commands (described below) for each commit to be rebased. These commands determine how individual commits will be transferred to the new base. You can also reorder the commit listing to change the order of the commits themselves.

If you would like more information/commands, please use your favourite search engine to look for it. Git is widely used throughout the world and there are many good tutorials and git related Q&A threads out there.

You can also visit [ohshitgit.com](http://ohshitgit.com/), a great site to help you ***git out of you git messes*** really quickly.
