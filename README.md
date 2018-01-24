# <img src="https://raw.githubusercontent.com/addy-org/Wiki/master/readme_assets/logo.png" alt="Addy" height="42" width="42"></img>  Addy-Wiki

[![Join the chat at https://gitter.im/addy-org/Wiki](https://badges.gitter.im/addy-org/Wiki.svg)](https://gitter.im/addy-org/Wiki?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/addy-org/Wiki.svg?branch=master)](https://travis-ci.org/addy-org/Wiki)

Official Documentation Website for Addy, based on a Jekyll Theme named [Paper](https://github.com/mkchoi212/paper-jekyll-theme)

### Website hosted at [addy.wiki](http://addy.wiki)

## Gitter channel link
https://gitter.im/addy-org

## Contribution Guidelines
https://addy.wiki/contribution-guidelines

## Running the site in your local system
```
git clone https://github.com/addy-org/Wiki
bundle install
rake preview
```

Then, go to your favourite browser and type in the address `http://127.0.0.1:YOUR_PORT_NUM_HERE`

## Adding Documentations

For adding a documentation, just create a new file in the `_documentations` folder. It will automatically be listed in the docs section. Follow the below format.

*Note: The file name will be the link of the post you added, like `https://addy.wiki/<FILE_NAME>/`*

```Markdown
---
layout: post
title: "<YOUR-TITLE-HERE>"
description: "<WRITE-A-SHORT-DESCRIPTION-ABOUT-THE-POST>"
tags: <INDIVIDUAL-TAGS-SEPARATED-BY-SPACE>
comments: true
---

<YOUR-CONTENT-HERE-IN-GITHUB-FLAVOURED-MARKDOWN>
```

## Adding Pages

For adding a new page, create a new file in the `_pages` folder. A page is not listed automatically, you have to link it to appropriate places.

```Markdown
---
layout: content
title: "<YOUR-TITLE-HERE>"
description: "<WRITE-A-SHORT-DESCRIPTION>" //optional
permalink: /<LINK-TO-THE-POST>/
---

<YOUR-CONTENT-HERE-IN-GITHUB-FLAVOURED-MARKDOWN>
```

## Getting Started with Contributing:
https://addy.wiki/newcomers-guide
