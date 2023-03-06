# Migration from Hexo to Hugo


# How this blog was created

In 2015, I built this blog with [Hexo](https://hexo.io/) and [Theme Octo](https://github.com/jbreckmckye/hexo-theme-octo).

# Why I migrate to Hugo

[Hugo](https://gohugo.io/) is written in Golang and it's much faster.

# How to migrate

## Installations

### Install Git and Go

### Install Hugo

``` bash
brew install hugo
```

## Create a site

``` bash
hugo new site blog
```

## Pick a theme

There are a bunch of [Hugo Themes](https://themes.gohugo.io/) for you to pick. I picked the [DoIt](https://themes.gohugo.io/themes/doit/) theme.

### Why I chose DoIt

There are so many exciting features, like mobile-friendly, search, i18n, emoji. The full feature list is [here](https://github.com/HEIGE-PCloud/DoIt#why-choose-doit)

### Use the theme

There are two ways to use the theme you chose above.

``` bash
git init
git clone https://github.com/HEIGE-PCloud/DoIt.git themes/DoIt
```

or 

``` bash
git clone https://github.com/HEIGE-PCloud/DoIt.git themes/DoIt
```

## Create a blog post

``` bash
hugo new posts/first_post.md
```

## Migrate Hexo posts

### Copy the posts

Execute the following commands in the root directory, which is *blog* here.

``` bash
cd content
mkdir posts
```
Then copy all your Hexo posts to the folder *posts*

### NB

After the site was created, there would be a template for new post like below in the file *$site$/archetypes/default.md*

``` bash
---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
---
```

You should assign false to the **draft** item to publish your blog.


## Preview the blog
Just run the command below to preview your site at *http://localhost:1313/*

``` bash
hugo server
```

## Publish the blog

### Create a Github repostory

Before publishing, you have to create a repo on Github like this

``` bash
https://$USERNAME$.github.io/
```

### Publish with commands

Commands for publishing your blog posts.

``` bash
cd public
git init
git remote add upstream https://github.com/$USERNAME$/$USERNAME$.github.io.git

git add .
git commit -m  "first commit"
git push -u origin main
```

### Build a shell script to publish

To do the deployment easier, you can build a shell script named *deploy.sh* in the root directory of you site with the content below.

``` bash
#!/bin/bash

echo -e "\033[0;32mDeploying updates to GitHub...\033[0m"

# build the project
hugo -t even

cd public

git add .

msg="rebuilding site `date`"

if [ $# -eq 1 ]
  then msg="$1"
fi

git commit -m "$msg"

# push source to github

git push upstream master

# come back to blog root

cd ..
```

And assign execution permission to *deploy.sh*

``` bash
chmod u+x deploy.sh
```

Next time when you need to publish, you just run

``` bash
./deploy.sh
```

## Other issues

### Date Time format

The strict/full format in Hugo is like below.

``` bash
YYYY-MM-DD HH:MM:SS +0800
```
The timezone detail *+0800* is not required, but sometimes you have to be very careful. e.g. A post is for en locale, the date in the West is March 5th while it's March 6th in your location already. If you specify the date as Marc 6th, your post would not be publish as expected(depends on the time).

This means the datetime has to be consistent with the locale.


