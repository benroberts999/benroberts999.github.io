---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

A selection of slides from some recent presentations and public talks:

{% for pres in site.presentations reversed %}

**{{ pres.title }}**, _{{ pres.conference }}_; {{ pres.host }}. — _{{ pres.date | date: "%B %Y" }}_
{{ pres.content }}

{% endfor %}
