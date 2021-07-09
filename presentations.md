---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

Test

{% for pres in site.presentations reversed %}
 <article class="post">

   * **{{ pres.title }}**
  <!-- <h4>{{ pres.conference }}. {{ pres.host }}. {{ pres.content }}<h4> -->
   _{{ pres.conference }}_; {{ pres.host }}. {{ pres.content }}<h4>

 {% endfor %}
