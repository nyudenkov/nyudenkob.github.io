---
layout: default
title: Archive
---

# Archive

All posts chronologically:

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in posts_by_year %}
## {{ year.name }}

{% for post in year.items %}
- **{{ post.date | date: "%B %d" }}** - [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}

{% endfor %}

{% if site.posts.size == 0 %}
*No posts yet.*
{% endif %}