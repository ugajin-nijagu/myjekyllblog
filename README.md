## README.md

#### Using jekyll with pages

This exersise is about using GitHub Pages to render a  jekyll boilerplate site. It had been anticpated that [https://help.github.com/articles/using-jekyll-with-pages](https://help.github.com/articles/using-jekyll-with-pages) would explain how to do this.

Perhaps, the reader of **GitHub**Help is intended to extrapolate the how, but for a greenhorn like me the solution is not at all obvious. It may be possible to extrapolate the solution in part, e.g. creating a `gh-pages` fork, but you also need to dig deeper to find the necessary remaining information.

You can find this missing information on Project Pages under Project Page URL Structure, See: [http://jekyllrb.com/docs/github-pages/](http://jekyllrb.com/docs/github-pages/). 

- In a text editor open, and edit the boilerplate file named: **_congig.yml** so that e.g. it reads as shown below:

~~~ 
baseurl: "/project-name" 
~~~

- `project-name` will be the same as your GitHub repository name. 

- to view the boilerplate site locally, after making this change use: `http://127.0.0.1:4000/project-name/`