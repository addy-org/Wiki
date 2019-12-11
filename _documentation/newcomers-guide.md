---
layout: post
title: "Newcomers Guide"
description: "A documentation help for newcomers to contribute in Addy"
tags: newcomers guide quick-start contribution
comments: true
---

**Please do not work on any issue without being assigned to it!** The reason for that is we will not know if you're are working on it and there might be a possibility that someone else might also be working on it. Hence, to avoid clashes and to contribute rightly please read and follow this guide.


This [Code of Conduct](../code-of-conduct/) has to be followed by each an every member of the organisation


# Getting Started
To get started, there are a few steps to be followed.

## 1. Join our community
### 1.1 Join our Gitter chatroom [here](https://gitter.im/addy-org/Lobby)

The first step of contributing in open source is always to get familiar with the community you're working with. Our mode of communication is mostly Gitter. Gitter is an instant messaging service used by developers and users of GitHub. Gitter uses chatrooms, where developers can join in and can talk about a particular topic. Addy has a common chatroom `Lobby` which is a common chatroom used for all the communications & discussion within the organisation and repository chatrooms which are related to a specific repository/ project.

List of all the chatrooms is available [here](https://gitter.im/addy-org)

But before joining the community, here are few things that you should keep in mind.
> - Only log into Gitter using your GitHub account and not your Twitter account since it might get difficult for us to know which GitHub user is really contributing and discussing the project with us. Also in future when we wish to automise the organisation, then the chatbots might have trouble identifying you.
- Don’t @-mention or private message people, unless its utterly important. @ mentions generate notifications on the various gitter clients the user may be signed into, you might even wake someone on the other side of the world up. Also it discourages other people to answer the question, so you might wait longer for an answer.
- Do not mention users unrelated to a particular issue/question. This also means you should not mention the person that was last online. For example, mentioning someone on a Github issue will subscribe them to that issue, even if they don’t want to be a part of the discussion. However, mentioning someone is okay if they really need to see your message.
- Don’t use /all if you are a newcomer or do not have a critical reason.
- Don’t repeatedly @-mention people in an ongoing conversation.
- You should ask someone before mentioning them.

### 1.2 Join the Addy organisation [here](http://bit.ly/JoinAddy).

Just click on the link and the invitation will be sent by mail and you will have to accept it to join. If you don’t find the invitation, accept it [here](https://github.com/addy-org/).


**Congratulations!** Now that you are part of Addys, you can start working on issues. If you are familiar with git, you can skip the next section and pick an issue.
<hr />
## Optional. Get Help With Git

We use GitHub to manage our repositories. If you’re not familiar with git/GitHub, we strongly recommend following a tutorial, such as [this one](https://try.github.io/levels/1/challenges/1).

We also have a [page dedicated to git commands](../git-tutorial/) that will help you learn the basics.

If anything is unclear, or you are encountering problems, feel free to contact us on gitter, and we will help you!
<hr />
## Step 2. Picking Up an Issue

Now it is time to pick an issue. It is the best way to familiarise yourself with the codebase. You can view [all Newcomer issues on GitHub](https://github.com/search?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+user%3Aaddy-org+label%3Anewcomers+no%3Aassignees).

> ***Note:*** *You need to be logged in before you follow the Newcomer issues link.*

The easy issues that will help you get started are labeled as newcomers and are only there to give you a glimpse of what it’s like to work with us and what the workflow is like.

Now pick an issue which isn’t assigned and which you would like to fix. Leave a comment that you would like to be assigned to the issue. Now ask on the Gitter channel for a maintainer to assign you the issue. Once one of the maintainers assign you the issue you can start working on it!

This way we don’t have multiple people working on the same issue at the same time.
<hr />
## Step 3. Creating a Fork

This tutorial assumes you are working on your own fork. To fork the repository, go to the official repository of addy-org and click on the ***Fork*** button from the website interface. To add it locally, simply run:
```bash
$ git remote add myfork fork_link
```
where `myfork` is the name of your fork, and `fork_link` is a link to your fork repository.
>**Note:**

>It is important that you DO NOT make your changes on the master branch of your forked repository to avoid the following cases:

>If you make a rebase to synchronize your repository to the original, every commit that is pushed to the remote master will be pulled in your master branch. Then if you make a pull request to commit your changes to the remote, the commits that got synced from the rebase will be recommitted along with your work in the pull request.

>You cannot have two pull requests using the same branch name. Therefore, if your fork’s master has been used in a pull request and you decide to work on a different issue you will have to branch eventually. Differently every new commit that you make on your master branch will get attached to the initial pull request and that will result in altering the purpose of that request.

>If your fork’s master has been used in a pull request, you have to keep the change in the branch until that get’s merged to the remote master. That will lead to the complications listed above, if you decide to work on a different issue.

>In order to avoid the above mentioned cases you can create a new branch where you will work on the issue. To do that run:

>```bash
$ git checkout -b <branchname>
```
<hr />
## Step 4. Sending Your Changes

Now that you’ve fixed the issue, you’ve tested it, and you think it is ready to be merged, create a commit and push it to your fork, using:
```bash
$ git push -u myfork <branchname>
```
<hr />
## Step 5. Creating a Pull Request

Now that your commit has been sent to your fork, it is time to create a Pull Request. You can do this by accessing your fork on GitHub and clicking New Pull Request.

**Congratulations!** You have now created your first Pull Request!

>**Note:** If you know you have more work to do on this Pull Request before it is ready to be accepted, you can indicate this to other developers by starting your Pull Request title with wip (case-insensitive, stands for “Work in Progress”).
<hr />
## Step 6. Review Process

After creating your Pull Request, it enters the review process. Now all you have to do is wait, or let the other developers know on Gitter that you have published your changes.

Now there are two possibilities:

- your `Pull Request` gets accepted, and your commits will get merged into the master branch
- your `Pull Request` doesn’t get accepted, and therefore you will need to to modify it as per the review comments

It’s highly unlikely that your Pull Request will be accepted on the first attempt - but don’t worry, that’s just how it works. It helps us keep Addy clean and stable.

Now, if you need to modify your code, you can simply edit it again, add it, and commit it using
```bash
$ git commit -a --amend
```
This will edit your last commit message. If your commit message was considered acceptable by our reviewers, you can simply send it again (without any changes). If not, edit it and send it. You have successfully edited your last commit!

> **Note:** Don’t forget! After editing your commit, you will have to push it again. This can be done using:

>```bash
$ git push --force myfork
```

The meaning of `myfork` is explained in step 3 of this guide. The Pull Request will automatically update with the newest changes.

**Congratulations!** Your PR just got accepted! You’re awesome. Now you should tell us about your experience and go for a low level issue - they are really rewarding!

>**Note:** If you need help picking up an issue, you can always ask us and we’ll help you!
