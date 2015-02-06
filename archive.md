---
layout: page
title: Archive
---
<!--- this is code to make a list of all the posts. 
## Blog Posts
{% for post in site.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}
--->

<!--- This code snippet parses all the tags and makes a list of the posts according to tags. --->
<!--- START --->
{% capture tags %}
  {% for tag in site.tags %}
    {{ tag[0] }}
  {% endfor %}
{% endcapture %}
{% assign sortedtags = tags | split:' ' | sort %}

{% for tag in sortedtags %}
  <h3 id="{{ tag }}">{{ tag }}</h3>
  <ul>
  {% for post in site.tags[tag] %}
    <li>{{ post.date | date_to_string }} - <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
{% endfor %}
<!--- END --->
