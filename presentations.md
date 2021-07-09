---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

{% for pres in site.presentations reversed %}

**{{ pres.title }}**, _{{ pres.conference }}_; {{ pres.host }}. — <span><h5>{{ pres.date | date: "%B %Y" }}</h5></span>
{{ pres.content }}

{% endfor %}
