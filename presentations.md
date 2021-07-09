---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

Test 2

{% for pres in site.presentations reversed %}

   * **{{ pres.title }}**
  <!-- <h4>{{ pres.conference }}. {{ pres.host }}. {{ pres.content }}<h4> -->
   _{{ pres.conference }}_; {{ pres.host }}. {{ pres.content }}<h4>

 {% endfor %}
