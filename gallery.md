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

new2

<style type="text/css">
#wrap {
  overflow: hidden;
}
.box {
  width: 50%;
  padding-bottom: 10%;
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
  <div id="box">
     <div id="innerContent">
         <li><img src="{{ image.image_path }}" alt="{{ image.title}}"/></li>
     </div>
  </div>
  {% endfor %}
</div>
</ul>
