---
layout: page
title: Conferences & Presentations
permalink: /talks/
---

Test

{% for pres in site.presentations reversed %}
 <article class="post">

   <h3>{{ pres.title }}</h3>
   <div class="entry">
     <h4>{{ pres.conference }}. {{ pres.host }}. {{ pres.content }}<h4>
   </div>

 </article>
 {% endfor %}
