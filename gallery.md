---
layout: page
title: Photos
permalink: /photos/
images:
  - image_path: /photos/tawny.jpg
    portrait: true
    title: Tawney Frogmouth
  - image_path: /photos/wagtail.jpg
    title: Willie Wagtail
  - image_path: /photos/butterfly.jpg
  - image_path: /photos/femalefairywren.jpg
  - image_path: /photos/landscape.jpg
  - image_path: /photos/spider.jpg
  - image_path: /photos/malefairywren.jpg
  - image_path: /photos/blackcockatoo.jpg
  - image_path: /photos/bats.jpg
  - image_path: /photos/kook.jpg
  - image_path: /photos/heron.jpg
  - image_path: /photos/darter.jpg
  - image_path: /photos/bee.jpg
  - image_path: /photos/owl.jpg
  - image_path: /photos/marmot.jpg
  - image_path: /photos/magpie.jpg
  - image_path: /photos/flicker.jpg
  - image_path: /photos/blackbord.jpg
  - image_path: /photos/moth.jpg
  - image_path: /photos/rock.jpg
  - image_path: /photos/hawk.jpg
---

ok

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
.longbox {
  width: 50%;
  padding-bottom: 100%;
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


<ul class="photo-gallery">
<div id="wrap">
  {% for image in page.images %}
  {% if image.portrait %}
    <div class="longbox">
      <div class="innerContent">
        <img width="100%" src="{{ image.image_path }}" alt="{{ image.title}}"/>
      </div>
    </div>
  {% else %}
    <div class="box">
      <div class="innerContent">
        <img width="100%" src="{{ image.image_path }}" alt="{{ image.title}}"/>
      </div>
    </div>
  {% endif %}
  {% endfor %}
</div>
</ul>


<!-- <ul class="photo-gallery">
<div id="wrap">
  {% for image in page.images %}
  <div class="box">
    <div class="innerContent">
      {% if image.portrait %}
      <img height="100%" src="{{ image.image_path }}" alt="{{ image.title}}"/>
      {% else %}
      <img width="100%" src="{{ image.image_path }}" alt="{{ image.title}}"/>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
</ul> -->
