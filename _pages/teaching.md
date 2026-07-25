---
title: "Teaching"
layout: archive
permalink: /teaching/
---


## Lecture Notes

{% assign chapters = site.lessons | group_by: "chapter" | sort: "name" %}
{% for chapter in chapters %}
  {% assign sorted_lessons = chapter.items | sort: "lesson_order" %}
  <details class="dropdown-box">
    <summary>{{ chapter.name }}</summary>
    <ul>
      {% for lesson in sorted_lessons %}
        <li><a href="{{ lesson.url | relative_url }}">{{ lesson.title }}</a>{% if lesson.excerpt %} — {{ lesson.excerpt }}{% endif %}</li>
      {% endfor %}
    </ul>
  </details>
{% endfor %}
