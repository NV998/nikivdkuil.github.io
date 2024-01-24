---
title: Setting up a static website.
author: Niki
date: 2024-01-23 14:10:00 +0100
categories: [Blogging, Tutorial]
tags: [writing]
render_with_liquid: false
---

_Note: I have a windows laptop and I was lucky the theme was easy to set up._

The first step for my internship was setting up a static website, a place where I could store all my documentation.

### What you are gonna need

- [**Github desktop**](https://desktop.github.com)
- [**RubyInstaller**](https://rubyinstaller.org/downloads/)
- [**Git**](https://git-scm.com/downloads)
- [**Visual Code Studio**](https://code.visualstudio.com/download)

### Information sources

- https://www.sven-dekker.com/documentation/setting-up-a-static-website/
- https://laurafreyaweller.github.io/setting-up-a-static-website
- https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll
- https://talk.jekyllrb.com/t/unable-to-run-the-jekyll-in-vs-code/6718/7
- https://jekyllrb.com/docs/installation/windows/

The tutorials I followed,

- [**Jekyll installation guide**](https://jekyllrb.com/docs/installation/windows/)
- [**Theme setup**](https://chirpy.cotes.page/posts/getting-started/)

### The proces

Before we start make sure you have all of these programs downloaded.

- Github desktop
- Rubyinstaller
- Git
- Visual code studio

#### Setting up github.

(You can skip this step if you're gonna fork a theme (see step "Choosing a theme"))

First we need to set up a github repository, you do this by going to the [**github website**](https://github.com) here we are going to make a new repository by clicking the `new` button.

- As name put your website name.
- In the description we write what were gonna use the website for.
- Put it on `public`.
- Add a read.me file
- For .gitignore we are gonna choose to use `jekyll`.
- For the license we are gonna use `MIT`.

#### Open Github desktop.

Click on `clone repository` and look for the one you just created. This makes us able to adjust the repository locally and add files.

#### Installing ruby and jekyll.

We have installed Ruby which is necessary to install Jekyll. Ruby is a programming language and Jekyll is a ruby gem, gems are code you can use with Ruby projects. First we need to check if we have all the necessary files.

- Run the ruby+devkit installer.
- Click the `ridk install` on the last screen.
- Now press `3`, MSYS2 and MINGW development tool chain to install those.

Now that we have installed Ruby we are gonna double check.

- Open your Command prompt
- Type in `gem install jekyll bundler` to install Jekyll.
- Type in `jekyll -v` to check if its installed.
- Type in `ruby -v`, make sure the ruby version is above 2.5.0
- Next type `gem -v`, my version at the time was 3.4.10
- You will also need the bundler gem, you can install this by typing `gem install bundler`.

#### Visual code studio.

Next up we are gonna open visual code studio, we need to open up our local github repository. You can do this by clicking `File` -> `Open folder` and looking for the map where your Github repositories are stored.

#### Choosing a theme.

You can find a jekyll theme from multiple websites, here are some listed below.

- https://jekyllrb.com/docs/themes/

I used a really easy theme to install and just followed the instructions, other themes might require a bit more work.
The specific one I used is called [**Chirpy**](https://chirpy.cotes.page/posts/getting-started/) the creator has a detailed tutorial on how to set it up.

What I did with this theme is option 2 (Forking the project), so I could see all the files and adjust most of them.
You put in your name and write github.io behind it, this will create a NEW repository. So the step above "Setting up a Github" is useless. Then we repeat the steps above but with this forked repository so,

- Opening it in Github desktop.
- Downloading ruby and jekyll.
- Checking if we have all the gems.
- Opening it in Visual code studio.

If you don't fork a repository you will have to follow the steps the theme gave you.

#### Loading the website locally.

I had alot of problems with this step, I tried multiple themes but some were outdated so I suggest if one doesn't work you try it with another one to figure out the problem/errors.

In Visual code studio open a new terminal by clicking on `terminal` clicking on `new terminal`. On the right you will see what profile you're running, choose powershell (this is the same as the windows command prompt).
Now to see if you can locally launch your website type `jekyll serve`. This will give you a server adress where you can view the website. If you save your changes in Visual code studio they will load right away on the local website.

#### Loading the website through Github pages.

Now that you have your website working locally we can make it an actual website other people can visit aswell.

- Go to github.com.
- Go to your repository.
- Go to settings.
- Go to pages.
- Beneath `Build and deployement` press `Github actions`.
  (This did not work for me the first time, when I clicked on the website link it just showed me `---layout: home - Index page ---`)
  - I fixed this by going into the `Actions` tab.
  - Clicking on `new workflow`.
  - Scrolling down to pages and clicking on `Deploy Jekyll site to pages`.
  - Wait for it to load and the link should work!

#### Errors

Some error's I experienced and how to fix them.

Installing gems
: There were some errors when trying to install gems, this was because I was not in the right directory. The way to fix this is by making sure you're working in the right directory.
For example `C:\Users\USER\Documents\GitHub\` is not the right one so you type `cd` behind it and hit tab, this will toggle through the maps untill you get on the right one, a.k.a the local repository.
So that would be: `C:\Users\Nikiv\Documents\GitHub\nikivdkuil.github.io>` now it will be about to find all the right files.

Jekyll serve doesn't work
: I had setup 2 themes and tried to view them locally but when I typed `jekyll serve` it gave me errors. This was because the theme was too outdated and the gems did not line up. If this happens, try another theme and double check if all the gems are correctly installed.
