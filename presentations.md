---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

Test 4

{% for pres in site.presentations reversed %}

   * **{{ pres.title }}**\
   _{{ pres.conference }}_; {{ pres.host }}. <div>{{ pres.content }}</div>

 {% endfor %}
