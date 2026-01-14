---
title: "News"
permalink: /news/
layout: single
author_profile: true
---

{% assign news_items = site.data.news | sort: "date" | reverse %}

{% for item in news_items %}

{% if item.type %}
<span style="
  display: inline-block;
  font-size: 0.75em;
  font-weight: 600;
  letter-spacing: 0.05em;
  color: #555;
  border: 1px solid #ddd;
  padding: 2px 8px;
  border-radius: 12px;
  margin-bottom: 6px;">
  {{ item.type | upcase }}
</span>
{% endif %}

### {{ item.title }}
<span style="color: #666;">{{ item.date | date: "%B %d, %Y" }}</span>

{% if item.description %}
{{ item.description }}
{% endif %}

{% if item.links %}
<p>
  {% for l in item.links %}
    <a href="{{ l.url }}">{{ l.label }}</a>{% unless forloop.last %} · {% endunless %}
  {% endfor %}
</p>
{% endif %}

---
{% endfor %}
