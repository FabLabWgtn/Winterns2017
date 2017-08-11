---
layout: default
title: Blog
---
Maybe this works
<!-- Posts -->
{% include blog.html %}

<ul id="posts">

	{% for post in paginator.posts %}

	  <li class="post">
	  	<h2><a href="{% if site.baseurl == "/" %}{{ post.url }}{% else %}{{ post.url | prepend: site.baseurl }}{% endif %}">{{ post.title }}</a></h2>
	  	<time datetime="{{ post.date | date_to_xmlschema }}" class="by-line">{{ post.date | date_to_string }}</time>
          {% if post.intro != null %}
          <p>{{post.intro}}</p>
          {% endif %}
	  </li>

    {% endfor %}

</ul>