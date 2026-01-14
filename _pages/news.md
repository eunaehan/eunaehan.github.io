---
title: "News"
permalink: /news/
layout: single
author_profile: true
---

{% assign news_items = site.data.news | sort: "date" | reverse %}

{% for item in news_items %}
### {{ item.title }}
<span style="color: #666;">{{ item.date | date: "%B %d, %Y" }}</span>

{% if item.link %}
- **Link:** [Read more]({{ item.link }})
{% endif %}

{% if item.description %}
{{ item.description }}
{% endif %}

---
{% endfor %}
