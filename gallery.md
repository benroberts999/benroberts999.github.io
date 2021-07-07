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

new

<style type="text/css">
#box {
   width: 25%;
   padding-bottom: 25%;
   background: #00F;
   color: #FFF;
   position: relative;
}
#innerContent {
   position: absolute;
   left: 10px;
   right: 10px;
   top: 10px;
   bottom: 10px;
   background: #66F;
}
</style>

<!-- <ul class="photo-gallery">
  {% for image in page.images %}
    <li><img src="{{ image.image_path }}" alt="{{ image.title}}"/></li>
  {% endfor %}
</ul> -->


<div id="box">
   <div id="innerContent">
       Absolutely-positioned content isn't counted in the parent's height!
   </div>
</div>
