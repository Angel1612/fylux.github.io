---
layout: page
title: Articles
---
<table>
{% for post in site.posts %}    
<tr>
    <td style="text-align:left;"><h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3></td>
    <td style="text-align:right;">{{ post.date | date_to_string }}</td>
</tr>
{% endfor %} 
</table>