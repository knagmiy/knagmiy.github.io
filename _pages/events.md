---
layout: page
title: Events
permalink: /events/
nav: true
nav_order: 1
---
Here is a list of events and conferences that I will attend/have attended.

{% assign today = site.time | date: "%Y%m%d" | plus: 0 %}
{% assign events = site.data.events | sort: "date" %}

**Upcoming**
<ul>
{% for e in events %}
  {% assign last = e.end_date | default: e.date | date: "%Y%m%d" | plus: 0 %}
  {% if last >= today %}{% include event_item.liquid e=e %}{% endif %}
{% endfor %}
</ul>

**Past**
<ul>
{% for e in events reversed %}
  {% assign last = e.end_date | default: e.date | date: "%Y%m%d" | plus: 0 %}
  {% if last < today %}{% include event_item.liquid e=e %}{% endif %}
{% endfor %}
</ul>
