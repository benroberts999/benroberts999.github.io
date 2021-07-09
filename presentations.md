---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

A selection of slides/posters from various conferences are available:(8)

{% for pres in site.presentations reversed %}

**{{ pres.title }}**, _{{ pres.conference }}_; {{ pres.host }}.
{{ pres.content }}

{% endfor %}
