---
layout: page
title: Lecture Notes
permalink: /lectures/
---

Lecture notes are supplement to the Learning Outcomes and Study Materials shared with you throughout the course on Blackboard.

{% assign items = site.lectures | sort: "order" %}
{% for lec in items %}
[{{ lec.title }}]({{ lec.url }})
{% endfor %}
