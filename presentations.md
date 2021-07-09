---
layout: page
title: Conferences & Presentations
permalink: /talks/
---


{% for pres in site.presentations reversed %}
 <article class="post">

   <h2>{{ pub.title }}</h2>
   <div class="entry">
     <h3>{{ pub.conference }}<h3>
     <h4>{{ pub.host }}<h4>
     {{ pub.content }}
   </div>

 </article>
 {% endfor %}
