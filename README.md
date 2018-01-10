# <img src="https://github.com/addy-org/Wiki/blob/master/readme_assets/logo.png" alt="Addy" height="42" width="42"></img>  Addy-Wiki

[![Join the chat at https://gitter.im/addy-org/Wiki](https://badges.gitter.im/addy-org/Wiki.svg)](https://gitter.im/addy-org/Wiki?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Official Documentation Website for Addy, based on a Jekyll Theme named [Paper](https://github.com/mkchoi212/paper-jekyll-theme)

### Website hosted at [addy.wiki](http://addy.wiki)

## Gitter channel link
https://gitter.im/addy-org

## Running the site in your local system
```
git clone https://github.com/addy-org/Wiki
bundle install
rake preview
```

Then, go to your favourite browser and type in the address `http://127.0.0.1:YOUR_PORT_NUM_HERE`

### Customisation
To customise various details - title/description of the website, your SNS account names, etc - edit the `_config.yml` file.

### Adding posts
```
rake post title="A Title" [date="2012-02-09"] [tags=[tag1,tag2]] [category="category"]
```
This will create a markdown file in the default folder where all posts are stored in Jekyll; `_post`.

If you wish to **change the directory where posts are saved**, go to the `Rakefile` and edit the `CONFIG = { 'posts': CUSTOM_PATH_HERE }`. This will allow `rake post` to know where to save the new posts to.

The **drafts** you are working on can be saved in the `_drafts` directory. When you push your code to the server, files in this directory will NOT be included to the list o posts.
