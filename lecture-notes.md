---
layout: page
title: Lecture Notes
permalink: /lectures/
---

Lecture notes are supplement to the Learning Outcomes and Study Materials shared with you throughout the course on Blackboard.

<style>
.lecture-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.lecture-card {
  background: #fff;
  border: 1px solid #e8e8e8;
  border-radius: 6px;
  padding: 1.2rem;
  transition: box-shadow 0.2s, transform 0.2s;
  text-decoration: none;
  color: inherit;
  display: block;
}

.lecture-card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  transform: translateY(-2px);
  text-decoration: none;
}

.lecture-top-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.75rem;
  margin-bottom: 0.6rem;
}

.lecture-week {
  display: inline-block;
  background: #e3f2fd;
  color: #1976d2;
  padding: 0.3rem 0.75rem;
  border-radius: 4px;
  font-size: 0.8rem;
  font-weight: 500;
  line-height: 1;
}

.lecture-reading-time {
  font-size: 0.75rem;
  color: #666;
  white-space: nowrap;
  line-height: 1;
}

.lecture-title {
  font-size: 1rem;
  font-weight: 500;
  color: #333;
  margin-bottom: 0.75rem;
  line-height: 1.4;
}

.lecture-meta {
  display: flex;
  flex-direction: column;
  gap: 0.4rem;
  font-size: 0.8rem;
  color: #666;
  border-top: 1px solid #f0f0f0;
  padding-top: 0.6rem;
  margin-top: 0.6rem;
}

.lecture-meta-item {
  display: flex;
  align-items: flex-start;
  gap: 0.5rem;
}

.lecture-meta-item strong {
  color: #555;
  font-weight: 500;
  min-width: 70px;
}
</style>

<div class="lecture-grid">
{% assign items = site.lectures | sort: "order" %}
{% for lec in items %}

  {% assign words = lec.content | number_of_words %}
  {% if words < 360 %}
    {% assign reading_time = "1 min" %}
  {% else %}
    {% assign reading_time = words | divided_by: 180 | append: " min" %}
  {% endif %}

  <a href="{{ lec.url }}" class="lecture-card">
    <div class="lecture-top-row">
      {% if lec.week %}
        <div class="lecture-week">
          Week
          {% if lec.week.first %}
            {{ lec.week | join: ", " }}
          {% else %}
            {{ lec.week }}
          {% endif %}
        </div>
      {% else %}
        <div></div>
      {% endif %}

      <div class="lecture-reading-time">⏳ {{ reading_time }}</div>
    </div>

    <div class="lecture-title">{{ lec.title }}</div>

    {% if lec.updated %}
    <div class="lecture-meta">
      <div class="lecture-meta-item">
        <strong>Updated:</strong> <span>{{ lec.updated }}</span>
      </div>
    </div>
    {% endif %}
  </a>

{% endfor %}
</div>
