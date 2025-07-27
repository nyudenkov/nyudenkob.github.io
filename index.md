---
layout: default
title: Home
---

# Recent Posts

<ul class="post-list">
{% for post in site.posts limit:10 %}
  <li class="post-list-item">
    <div class="post-list-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </div>
    <div class="post-list-date">{{ post.date | date: "%Y-%m-%d" }}</div>
    {% if post.excerpt %}
    <div class="post-list-excerpt">{{ post.excerpt | strip_html | truncatewords: 25 }}</div>
    {% endif %}
  </li>
{% endfor %}
</ul>

{% if site.posts.size == 0 %}
<p class="no-posts">No posts yet.</p>
{% endif %}