---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

Test 3

{% for pres in site.presentations reversed %}

   * **{{ pres.title }}**\
   _{{ pres.conference }}_; {{ pres.host }}. {{ pres.content }}

 {% endfor %}
