---
layout: page
title: Conferences & Presentations
permalink: /slides/
---

_A selection of slides from some recent presentations and public talks:_

{% for pres in site.presentations reversed %}

**{{ pres.title }}**, _{{ pres.conference }}_; {{ pres.host }}. — _{{ pres.date | date: "%B %Y" }}_
{{ pres.content }}

{% endfor %}
