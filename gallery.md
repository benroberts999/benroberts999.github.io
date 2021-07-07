---
layout: page
title: Photos
permalink: /photos/
images:
  - image_path: /photos/404.jpg
    title: Apple Pie
  - image_path: /photos/ben.jpg
    title: Birthday Cake
---

<ul class="photo-gallery">
  {% for image in page.images %}
    <li><img src="{{ image.image_path }}" alt="{{ image.title}}"/></li>
  {% endfor %}
</ul>
