## README.md

#### Using jekyll with pages

[https://help.github.com/categories/github-pages-basics/](https://help.github.com/categories/github-pages-basics/)

This README file documents the process for using jekyll to generate a boilerplate site, which is then rendered with GitHub Pages, using OS X v10.11.1. It contains what I think are the essential details that I had anticipated, and not found on **GitHub**Help. I had anticpated that [https://help.github.com/articles/using-jekyll-with-pages](https://help.github.com/articles/using-jekyll-with-pages) would explain how to use jekyll and GitHub Pages. 

This README.md file documents the following topics:

1. Building a boilerplate jekyll site
- Viewing the site locally
- Editing `_config.yml`
- Building the local repository
- Creating a GitHub repository
- Connecting repositories
- Viewing the GitHub Pages site

It is assumed that:

- Git is both installed and configured
- Ruby is intalled
- That jekyll is installed
- You have a GitHub account

* * *

### Viewing hidden files on OS X

On OS X, files prefixed with a `.` (period) are hidden by default. This will include files such as a local `.git` repository. By default you won't see anything happen in Finder  when you run the `git init` command.  

There is a Terminal command, which can be used to toggle system file visiblity on and off. Making system files visible may help you to explore both file content, and the structure of a local Git repository using Finder.

To enable visibility, type the following command (without the `$` sign), in a Terminal window and press the return/enter key:

~~~bash
$ defaults write com.apple.finder AppleShowAllFiles TRUE

$ killall Finder
~~~

The first command tells Finder to show hidden files and the second command restarts Finder.

After telling Finder to show hidden files, we need to restart Finder. Alternatively, you can restart Finder manually, from the Dock, by hitting `⎇ + right click` on the Finder icon, and selecting `Relaunch` from the control menu options.

To reset Finder to its default state run:

~~~bash
$ defaults write com.apple.finder AppleShowAllFiles FALSE

$ killall Finder
~~~

* * *

### Building the jekyll boilerplate site

- To make a jekyll boilerplate site, open Terminal and run the following command:

~~~ bash
$ jekyll new blog
~~~

These instruction which can also be found at: a[http://jekyllrb.com/docs/quickstart/](http://jekyllrb.com/docs/quickstart/), will create a folder containing a boilerplate site. By default Terminal locates to the user's home directory where a directory named `blog` is created with the boilerplate jekyll site inside.

* * *

### Viewing the site locally

- To view the boilerplate site locally, run the following commands: 

~~~ bash
$ cd blog
~~~

In order to run the `jekyll serve` command, we must relocate the Terminal window changing its current, or working  directory to the folder containing the boilerplate site.

~~~ bash
$ jekyll serve
~~~

Then point your browser to:

<pre>
http://127.0.0.1:4000
</pre>

See: [http://jekyllrb.com/docs/usage/](http://jekyllrb.com/docs/usage/)

> Jekyll also comes with a built-in development server that will allow you to preview what the generated site will look like in your browser locally.

* * *

### Editing `_config.yml`

There is one small, but essential detail that is missing from **GitHub**Help and **Using Jekyll with Pages** assuming that is, that you are looking to see your boilerplate site on GitHub Pages. 

As we saw previously, you do not need to do anything to the boilerplate site in order to view it locally, but you will need to make a small adjustment before you are able to render, and view the site on GitHub Pages. 

You can find the missing information on Project Pages under Project Page URL Structure, See: [http://jekyllrb.com/docs/github-pages/](http://jekyllrb.com/docs/github-pages/).

- In a text editor open, and edit the boilerplate file named: **_congig.yml** so that it reads as shown below:

~~~ 
baseurl: "/project-name" 
~~~

Note the leading slash, the absence of a trailing slash. The that project-name will be the name of your GitHub repository (see below: Creating a GitHub repository). You can replace `project-name` with anything you like. 

After making this change you will no longer be able to view the boilerplate site locally using: `http://127.0.0.1:4000`. Instead you will need to go to:

<pre>
http://127.0.0.1:4000/project-name/
</pre>

* * *

### Building the local repository

We have a boilerplate site, which we can render locally, but we still need to create a local Git repository for the site. To create our local repository we will be running git commands in Terminal.

- In Terminal run the following 3 commands (again without the `$` sign):

~~~ bash
$ git init
~~~

~~~ bash
$ git add .
~~~

~~~ bash
$ git commit -m 'first commit'
~~~

You should see Terminal generate information e.g.

~~~
[master (root-commit) af8345e] first commit
 22 files changed, 902 insertions(+)
 create mode 100644 .gitignore
 create mode 100644 _config.yml
 create mode 100644 _drafts/draft-blog.md
 create mode 100644 _includes/footer.html
 create mode 100644 _includes/head.html
 create mode 100644 _includes/header.html
 create mode 100644 _includes/icon-github.html
 create mode 100644 _includes/icon-github.svg
 create mode 100644 _includes/icon-twitter.html
 create mode 100644 _includes/icon-twitter.svg
 create mode 100644 _layouts/default.html
 create mode 100644 _layouts/page.html
 create mode 100644 _layouts/post.html
 create mode 100644 _posts/2015-12-24-welcome-to-jekyll.markdown
 create mode 100644 _posts/2015-12-30-hello-world.md
 create mode 100644 _sass/_base.scss
 create mode 100644 _sass/_layout.scss
 create mode 100644 _sass/_syntax-highlighting.scss
 create mode 100644 about.md
 create mode 100644 css/main.scss
 create mode 100644 feed.xml
 create mode 100644 index.html
~~~
 
In addition, if you have a Finder window open on the `blog` directory, you will be able to observe Git create and populate the repository , and spend some time exploring its files and folders.

* * *

### Creating a GitHub repository

Next we need to build a GitHub repository which we will then connect with our local repository. This is done online using your GitHub account.

- Open GitHub, and and log in to your account
- Create a new repository.   
In the upper-right corner of any GitHub page, click the `+` control button, and select `New repository` from the drop down menu.
- Give the repository the same name as used for the `baseurl` property value; e.g. `project-name`
- Leave all the other options set to their default settings
- Use the `copy` control button to copy the git commands from the GitHub page, the one next to the section labelled:  
'…or push an existing repository from the command line'.  
This will copy the following git commands to the clipboard:

<pre>
git remote add origin https://github.com/ugajin-nijagu/project-name.git
git push -u origin master
</pre>

* * *

### Connecting repositories

To connect our repositories, paste the git commands which we saved to our clipboad into the Terminal window, and press the `return` key.

~~~ bash
$ git remote add origin https://github.com/ugajin-nijagu/myjekyllblog.git  
git push -u origin master
~~~

You should see Terminal generate code; e.g.

~~~
Counting objects: 30, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (27/27), done.
Writing objects: 100% (30/30), 10.19 KiB | 0 bytes/s, done.
Total 30 (delta 2), reused 0 (delta 0)
To https://github.com/ugajin-nijagu/myjekyllblog.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
apple-2s-iMac:blog apple_2$
~~~

You should also see all the necessary boilerplate files loaded into the GitHub repository. 

The boilerplate site includes a `gitignore` file. Files listed in this document are not connected. By default this includes the following files:

<pre>
_site
.sass-cache
.jekyll-metadata
</pre>

* * *

### Viewing the GitHub Pages site

Finally, to view the boilerplate site on GitHub we need to create a new `branch`. 

From the **`Branch:`** control on the GitHub repository page, create a new branch named:

<pre>
gh-pages
</pre>

Select the **`Settings`** page, and the published page's hyperlink url can be found under the **`GitHub Pages`** section.

Click on the link to view the boilerplate site.

* * *

~~~ yaml
---
title: "Macdown is my friend"  
date: 2014-06-06 20:00:00
---
~~~