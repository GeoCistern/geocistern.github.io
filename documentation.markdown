---
layout: page
title: Documentation
permalink: /documentation/
---

<ul class="posts-in-list">
      {% for post in site.posts %}
        <li class="post-list">
            <!--    <span class="date">{{ post.date | date: '%B %d, %Y' }}</span>  -->

            <h3><a href="{{ site.baseurl }}{{ post.url }}" style="color:black; text-decoration:underline">{{ post.title }}</a></h3>
            <p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 250 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 250 }}{% endif %}</p>
        </li>
      {% endfor %}
</ul>
