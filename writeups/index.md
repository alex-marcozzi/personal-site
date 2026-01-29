---
layout: default
title: Writeups
permalink: /writeups/
---

# Writeups

{% assign writeups_sorted = site.writeups | sort: 'date' | reverse %}

{% if writeups_sorted.size == 0 %}
No writeups yet.
{% else %}
<ul class="writeups-list">
  {% for writeup in writeups_sorted %}
    <li>
      <a href="{{ writeup.url | relative_url }}">{{ writeup.title }}</a>
      {% if writeup.date %}
        <span class="meta">{{ writeup.date | date: "%Y-%m-%d" }}</span>
      {% endif %}
      {% if writeup.description %}
        <div class="description">{{ writeup.description }}</div>
      {% endif %}
    </li>
  {% endfor %}
</ul>
{% endif %}
