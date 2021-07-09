---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

A selection of slides/posters from various conferences are available:(2)

{% for pres in site.presentations reversed %}

   * **{{ pres.title }}**\
   _{{ pres.conference }}_; {{ pres.host }}. {{ pres.slides }}

{% endfor %}
