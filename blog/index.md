---
layout: page
title: This is the blog page
---
{% include JB/setup %}


<ul class="posts">
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {% if post.content contains '<!--more-->' %}
    {{ post.content | split:'<!--more-->' | first }}
     <a href="{{ post.url }}">Read More</a>
{% else %}
    <!-- Case for when no excerpt is defined -->
{% endif %}
    </li>
  {% endfor %}
</ul>