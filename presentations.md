---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

{% for pres in site.presentations reversed %}

**{{ pres.title }}**, _{{ pres.conference }}_; {{ pres.host }}.<h5> — {{ page.date | date: "%B %Y" }}</h5>
{{ pres.content }}

{% endfor %}
