---
layout: post
title: "Adding CI to your Fork"
description: "This tutorial will help you add the CI tools, that are used in our repositories to test the code, to your forked repository."
tags: git GitHub tutorial
comments: true
---
Before we start adding CI it’s important you have a GitHub account and know how to fork repositories. In case you don’t, you should have a look into our [Git Tutorial](../git-tutorial).

# Travis CI

Travis is used to confirm that the tools install and build properly. It also runs the tests and confirms all test cases pass and have 100% coverage. These are examples of travis CI checks used in Addy repositories:
- <https://travis-ci.org/addy-org/Addy-Android/builds/328710806>
- <https://travis-ci.org/addy-org/Wiki/builds/328024820>.

To run identical CI checks in travis you will need to configure your forked repository and to do that follow the steps mentioned below.

1. Go to [travis-ci.org](https://travis-ci.org) and create an account. You can simply use your GitHub account for that.
2. On the top left corner you will see a “+” icon beside “My Repositories”. Click on that, and it will take you to your travis-ci profile.
3. Sync your account with GitHub by clicking on the top right button saying “Sync account”.
4. Find the forked Addy repository in the list and enable builds for it.
5. Travis CI requires a .travis.yml file containing the settings and build instructions. Your forked repository from Addy will already have that file.
6. Watch the builds at travis-ci.org/*username*/*repository*/builds.

# Codecov

We require 100% test coverage, and to test that we use codecov.io which takes data from all other CI to confirm its coverage. Follow the instructions here, to enable getting coverage reports for your forked repository.

1. Go to codecov.io and sign up using your GitHub account.
2. Click on your username, and that will take you to a page where the repositories that use codecov are listed.
3. Click on “Add new repository” and it will take you to a page that lists all your repositories. Choose the forked repository for which you want to enable codecov.
4. Like other CI, this also has a configuration file, .codecov.yml file which your forked repository will already have. The CI uploads the test reports to codecov, which then creates an overall coverage report.
5. You can watch the reports at codecov.io/gh/*username*/*repository*
