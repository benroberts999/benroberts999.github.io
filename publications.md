---
layout: page
title: Publications
permalink: /publications/
---

Some information about you!

### More Information

<div class="posts">
  {% for pub in site.pubs %}
    <article class="publication">

      <h1><a href="{{ site.baseurl }}{{ pub.url }}">{{ pub.title }}</a></h1>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ pub.url }}" class="read-more">Read More</a>
    </article>
  {% endfor %}
</div>
