---
layout: page
title: Articles
---
<table>
{% for post in site.posts %}    
<h3>
    <tr>
    <td><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></td>
    <td><small>{{ post.date | date_to_string }}</small></td>
    </tr>
</h3>
{% endfor %} 
</table>