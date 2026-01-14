---
title: "News"
permalink: /news/
layout: single
author_profile: true
---
<hr style="
  margin: 0.5em 0 1.2em 0;
  border: none;
  border-top: 1px solid #e5e5e5;
">

{% assign news_items = site.data.news | sort: "date" | reverse %}

{% for item in news_items %}

{% if item.type %}
{% assign t = item.type | downcase %}

{% if t == "publication" %}
  {% assign color = "#2b6cb0" %}   {% comment %} blue {% endcomment %}
{% elsif t == "newsletter" %}
  {% assign color = "#2f855a" %}   {% comment %} green {% endcomment %}
{% elsif t == "talk" %}
  {% assign color = "#805ad5" %}   {% comment %} purple {% endcomment %}
{% elsif t == "presentation" %}
  {% assign color = "#b7791f" %}   {% comment %} amber {% endcomment %}
{% elsif t == "award" %}
  {% assign color = "#c53030" %}   {% comment %} red {% endcomment %}
{% elsif t == "grant" %}
  {% assign color = "#1a202c" %}   {% comment %} dark gray {% endcomment %}
{% elsif t == "media" %}
  {% assign color = "#2c7a7b" %}   {% comment %} teal {% endcomment %}
{% elsif t == "service" %}
  {% assign color = "#4a5568" %}   {% comment %} muted gray {% endcomment %}
{% else %}
  {% assign color = "#555" %}
{% endif %}


<span style="
  display: inline-block;
  font-size: 0.75em;
  font-weight: 600;
  letter-spacing: 0.06em;
  color: {{ color }};
  border: 1px solid {{ color }};
  padding: 3px 10px;
  border-radius: 14px;
  margin-bottom: 2px;">
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
    <a href="{{ l.url }}" target="_blank" rel="noopener noreferrer">{{ l.label }}</a>{% unless forloop.last %} · {% endunless %}
  {% endfor %}
</p>
{% endif %}

{% if item.image %}
<img src="{{ item.image }}"
     alt="{{ item.title }}"
     style="
       width: 300px;
       height: 300px;
       object-fit: cover;
       border-radius: 1px;
       margin-bottom: 1px;
     ">
{% endif %}

---
{% endfor %}
