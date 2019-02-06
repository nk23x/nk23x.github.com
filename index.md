* [gists](https://gist.github.com/nk23x/public?direction=desc&sort=updated)

{% for post in site.posts %}
* [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{% endfor %}