---
layout: page
title: Articles
---
{% for post in site.posts %}    
<h3 class="post-title">
     <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    <small>{{ post.date | date_to_string }}</small>
</h3>   
{% endfor %} 
