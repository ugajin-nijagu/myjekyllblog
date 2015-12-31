---
layout: post
title: "Hello, World!"
categories: jekyll update
---

# Highlighting Code Snippets

Jekyll also has built-in support for syntax highlighting of code snippets using either Pygments or Rouge, and including a code snippet in any post is easy. Just use the dedicated Liquid tag as follows; and the output will look like this:

{% highlight ruby linenos %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}

{% highlight css linenos %}
body {
width: 100%
}
{% endhighlight %}

{% highlight javascript linenos %}
Draw.vals = {to: '#svg_7', x: 320, y: 212,
           fill: 'brown', fillOpacity: 0.25,
           stroke: 'black', strokeWidth: 1,
           fontFamily: 'Georgia', fontSize: 160,
           fontWeight: 800, textAnchor: 'middle',
           letterSpacing: 4,
           filter: 'url(#myFilter_05)',
           textNode: 'Hello!'};
Draw.obj('text');
{% endhighlight %}

2015-12-28
