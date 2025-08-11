---
layout: single
title:
permalink: /math_main/
classes: wide
---


<article class="post">
  <header>
    <h1>{{ page.title }}</h1>
    <p class="post-meta">{{ page.date | date: "%B %d, %Y" }}</p>
  </header>

  <section class="post-content">
    {{ content }}
  </section>

  {% if page.documents %}
  <section class="post-documents">
    <h2>Documents</h2>
    <ul>
      {% for doc in page.documents %}
      <li><a href="{{ doc.url }}" target="_blank">{{ doc.name }}</a></li>
      {% endfor %}
    </ul>
  </section>
  {% endif %}
</article>
