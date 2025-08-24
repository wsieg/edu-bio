---
layout: single
title:
permalink: /math_main/
classes: wide
---


<h1>Mathématiques informations</h1>

<div class="announcements">
  {% for post in site.categories.math %}
  <div class="announcement-card">
    <div class="announcement-date">
      {{ post.date | date: "%B %d, %Y" }}
    </div>
    <div class="announcement-title">
      <a href="{{ post.url }}">{{ post.title }}</a>
    </div>
    <div class="announcement-content">
      {{ post.content }}
    </div>
    {% if post.documents %}
    <div class="announcement-documents">
      <strong>Documents:</strong>
      <ul>
        {% for doc in post.documents %}
        <li><a href="{{ doc.url }}" target="_blank">{{ doc.name }}</a></li>
        {% endfor %}
      </ul>
    </div>
    {% endif %}
  </div>
  {% endfor %}
</div>

<style>
.announcements {
  display: flex;
  flex-direction: column;
  gap: 1.5em;
}
.announcement-card {
  padding: 1em;
  border: 1px solid #ccc;
  border-radius: 8px;
  background: #fdfdfd;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}
.announcement-date {
  font-size: 0.9em;
  color: #777;
}
.announcement-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-top: 0.2em;
}
.announcement-content {
  margin-top: 0.5em;
}
.announcement-documents ul {
  margin-top: 0.3em;
  padding-left: 1.2em;
}
</style>
