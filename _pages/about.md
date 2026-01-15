---
permalink: /
title: "Welcome!"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am Dr. Eunae Han, a Licensed Professional Counselor (Texas), National Certified Counselor (NCC), and Assistant Professor in the Department of Counseling and Special Education at the University of Texas at El Paso (UTEP). My work centers on supporting future counselors and counselor educators through trauma-informed, social justice-oriented, and feminist approaches.

My research interests include **community-engaged scholarship**, **AI-assisted counselor education**, **trauma-informed counseling**, and **feminist perspective in counselor training**. I am passionate about bridging practice, pedagogy, and research to advance equity and wellness in both educational and clinical settings.  

Outside of my professional work, I enjoy practicing Kumdo/Kendo, traveling to new places with my husband, playing board games, and finding joy in quiet mornings with coffee and a good book.

Please feel free to contact me via email (<span style="color:#0055A4">dr.eunaehan@gmail.com</span>) if you have any questions or would like to discuss potential collaborations.

<hr style="margin: 1.0em 0 0.5em 0; border: none; border-top: 1px solid #e5e5e5;">

<h2 style="margin-bottom: 0.6em;">Highlights</h2>

{% assign recent_news = site.data.news | sort: "date" | reverse %}

<ul style="margin: 0; padding-left: 1.2em;">
  {% for item in recent_news limit:3 %}

    {% comment %} --- must match slug logic in news.md --- {% endcomment %}
    {% assign slug = item.date | append: "-" | append: item.title
      | downcase
      | replace: "&", "and"
      | replace: "—", "-"
      | replace: "–", "-"
      | replace: ":", ""
      | replace: ".", ""
      | replace: ",", ""
      | replace: "'", ""
      | replace: '"', ""
      | replace: "(", ""
      | replace: ")", ""
      | replace: "/", "-"
      | replace: "?", ""
      | replace: " ", "-"
    %}

    <li style="margin-bottom: 0.8em;">
      <a href="{{ '/news/#' | append: slug | relative_url }}" style="text-decoration: none;">
        <strong>{{ item.title }}</strong>
      </a><br>
      <span style="color:#666; font-size:0.95em;">
        {{ item.date | date: "%B %d, %Y" }}
        {% if item.type %} · {{ item.type }}{% endif %}
      </span>
    </li>

  {% endfor %}
</ul>

<p style="margin-top: 0.8em;">
  <a href="{{ '/news/' | relative_url }}">View all news →</a>
</p>
