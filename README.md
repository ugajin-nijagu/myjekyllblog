## README.md

#### Using jekyll with pages

This is an exersise in using GitHub Pages to render a  boilerplate sitemade with jekyll.

I had anticpated that [https://help.github.com/articles/using-jekyll-with-pages](https://help.github.com/articles/using-jekyll-with-pages) would explain this.

Perhaps, the reader of **GitHub**Help is intended to extrapolate how do render the locally jekyll generated site, using GitHub Pages, but for a greenhorn like me the solution is not at all obvious.

It may be possible to extrapolate the solution in part, e.g. by creating a `gh-pages` fork, but you also need to dig deeper to find the necessary remaining information.

You can find the missing information on Project Pages under Project Page URL Structure, See: [http://jekyllrb.com/docs/github-pages/](http://jekyllrb.com/docs/github-pages/). 

- In a text editor open, and edit the boilerplate file named: **_congig.yml** so that e.g. it reads as shown below:

~~~ 
baseurl: "/project-name" 
~~~

The project-name will be the same as your GitHub repository name. 

To view the boilerplate site locally, after making this change use: `http://127.0.0.1:4000/project-name/`