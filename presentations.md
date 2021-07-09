---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

{% for pres in site.presentations reversed %}

**{{ pres.title }}**, _{{ pres.conference }}_; {{ pres.host }}. — _{{ pres.date | date: "%B %Y" }}_
{{ pres.content }}

{% endfor %}
