---
layout: default
title: Home
---

# Recent Posts

<div class="post-list">
{% for post in site.posts limit:10 %}
  <div class="post-list-item">
    <h2 class="post-list-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>
    <div class="post-list-date">{{ post.date | date: "%B %d, %Y" }}</div>
    {% if post.excerpt %}
    <div class="post-list-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</div>
    {% endif %}
  </div>
{% endfor %}
</div>

{% if site.posts.size == 0 %}
<p>No posts yet.</p>
{% endif %}