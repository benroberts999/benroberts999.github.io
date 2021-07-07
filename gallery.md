---
layout: page
title: Photos
permalink: /photos/
images:
  - image_path: /photos/IMG_3413-Edit.jpg
    title: Tawney Frogmouth
  - image_path: /photos/IMG_5482-Edit.jpg
    title: Willie Wagtail
  - image_path: /photos/404.jpg
    title: Apple Pie
  - image_path: /photos/ben.jpg
    title: Birthday Cake
  - image_path: /photos/ben.jpg
    title: ben2
  - image_path: /photos/404.jpg
    title: ben3
---

width

<style type="text/css">
#wrap {
  overflow: hidden;
}
.box {
  width: 50%;
  padding-bottom: 50%;
  position: relative;
  float: left;
}
.innerContent {
  position: absolute;
  left: 1px;
  right: 1px;
  top: 1px;
  bottom: 1px;
  padding: 10px;
}
</style>

<!-- <ul class="photo-gallery">
  {% for image in page.images %}
    <li><img src="{{ image.image_path }}" alt="{{ image.title}}"/></li>
  {% endfor %}
</ul> -->




<ul class="photo-gallery">
<div id="wrap">
  {% for image in page.images %}
  <div class="box">
    <div class="innerContent">
      <img width="100%" src="{{ image.image_path }}" alt="{{ image.title}}"/>
    </div>
  </div>
  {% endfor %}
</div>
</ul>
