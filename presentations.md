---
layout: page
title: Conferences & Presentations
permalink: /talks/
---


{% for pres in site.presentations reversed %}
 <article class="post">

   <h2>{{ pres.title }}</h2>
   <div class="entry">
     <h3>{{ pres.conference }}<h3>
     <h4>{{ pres.host }}<h4>
     {{ pres.content }}
   </div>

 </article>
 {% endfor %}
