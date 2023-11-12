---
layout: page
title: Students
permalink: /students/
---

### Available projects at UQ (PhD, masters, honours, and undergraduate)

* [Atomic physics as a probe of the Standard Model at low energies](https://smp.uq.edu.au/project/atomic-physics-probe-standard-model)
* [Development of high-precision atomic structure methods](https://smp.uq.edu.au/project/development-high-accuracy-atomic-theory-methods)
* [Theoretical characterisation of systems for the development of atomic clocks](https://smp.uq.edu.au/project/theoretical-characterisation-systems-development-atomic-clocks)
* [Enlightening the search for dark matter (and other exotic physics)](https://smp.uq.edu.au/project/enlightening-search-dark-matter-and-other-exotic-physics)
* For more details, see: [researchers.uq.edu.au/researcher/24237](https://researchers.uq.edu.au/researcher/24237)
* Projects are flexible and other projects are available, contact me with any questions
* Formal applications are made through the University of Queensland -- [smp.uq.edu.au/study/higher-degree-research](https://smp.uq.edu.au/study/higher-degree-research). Feel free to contact me directly with any questions

<!-- Slides from most of my recent conference presentations can be found [here]({{ site.baseurl }}/talks) -->

## Current Students

 <!-- {% for student in site.students reversed %}
 <article class="post">

   <h1>{{ pub.title }}</h1>
   <div class="entry">
     {{ pub.content }}
     <hr>
   </div>

 </article>
 {% endfor %} -->

<div class="entry">
{% assign tstudent = site.students | reverse | where:'current', true %}
{% for student in tstudent %}
<article class="post">

  <h1>{{ student.name }}</h1>
  <div class="entry">
    {{ student.content }}
    <hr>
  </div>

</article>
{% endfor %}
</div>
