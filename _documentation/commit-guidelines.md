---
layout: post
title: "Commit Guidelines"
description: "The guidelines to be kept in mind while writing commit messages"
tags: commit guidelines quick-start contribution
comments: true
---

# Quick reference

Example of a good commit:

`Gemfile.lock: Update nokogiri version // Commit Message`

```
// Commit Description
This upgrades nokogiri version to 1.8.1
and hence other dependencies are updated too
This was done due to a potential security
vulnerability stated by GitHub
```

> *Gemfile.lock: Update nokogiri version:* Describe the change in
maximum of ***50 characters***.

> *This upgrades.. ..by GitHub:* Describe the reasoning of your changes
in maximum of ***72 characters per line***.

<hr />

`Update gem bundle // Commit Message`

```
// Commit Description
Fixes the travis build
```
> *Update gem bundle:* Describe the change in
maximum of 50 characters.

> *Fixes the travis build:* Describe the reasoning of your changes
in maximum of 72 characters per line.

***It is not always necessary to write a commit description, but the commit messages should follow the guide***

This guide will further explain the way of writing commit messages. Writing nice commit messages is an essential part of contributing in open source. Always remember, *Code is more often read than written!*. Hence we need good quality codes and great commit messages just enables the developers to easily identify the working of each piece of code.

# What Makes a Good Commit?
A good commit is atomic. It should describe one change and not more.

Why? Because we may create more bugs if we had more changes per commit.

# How to Write Good Commits
A commit consists of 2 parts:

- commit message
- commit description

Example:

`Gemfile.lock: Update nokogiri version // Commit Message`

```
// Commit Description
This upgrades nokogiri version to 1.8.1
and hence other dependencies are updated too
This was done due to a potential security
vulnerability stated by GitHub
```

## Commit Message

Example:

`Gemfile.lock: Update nokogiri version`

- **Maximum of 50 characters.** <br/>Keeping subject lines at this length ensures that they are readable, and explains the change in a concise way.
- Should **describe the change** - the action being done in the commit.

## Commit Description

Example:
```
This upgrades nokogiri version to 1.8.1
and hence other dependencies are updated too
This was done due to a potential security
vulnerability stated by GitHub
```

- **Maximum of *72 characters* excluding newline for *each line*.**<br />
The recommendation is to add a line break at 72 characters, so that Git has plenty of room to indent text while still keeping everything under 80 characters overall.
- **Not mandatory** - but helps explain what you’re doing.
- Should describe the reasoning for your changes. This is especially important for complex changes that are not self explanatory. This is also the right place to write about related bugs.

# Editing Commit Messages

If you have previously made a commit and update it on a later date, it is advisable to also update the commit message accordingly.

In order to do this one can use the amend function as is described [here](../git-tutorial).

*// Credits: our friends at [coala](coala.io)*
