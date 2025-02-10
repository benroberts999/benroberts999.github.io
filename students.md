---
layout: page
title: Students
permalink: /students/
---

### Available projects at UQ (PhD, masters, honours, and undergraduate)

* Atomic physics as a probe of the Standard Model at low energies
* Development of high-precision atomic structure methods
* Theoretical characterisation of systems for the development of atomic clocks
* Enlightening the search for dark matter (and other exotic physics)
* For more details, see: [researchers.uq.edu.au/researcher/24237](https://researchers.uq.edu.au/researcher/24237)
* Projects are flexible and other projects are available, contact me with any questions
* Formal applications are made through the University of Queensland -- [smp.uq.edu.au/study/higher-degree-research](https://smp.uq.edu.au/study/higher-degree-research). Feel free to contact me directly with any questions

<hr>

# Current PhD Students

<hr>

<div class="entry">
{% assign tstudent = site.students | reverse | where:'current', true %}
{% for student in tstudent %}
{% if student.type == "PhD" %}
<article class="post">

  <h2>{{ student.name }} ({{ student.type }} student, {{ student.university }})</h2>
  <div class="entry">
    {{ student.content }}
    <hr>
  </div>

</article>
{% endif %}
{% endfor %}
</div>

<hr>

# Current Honours/Masters Students

<hr>

<div class="entry">
{% assign tstudentB = site.students | reverse | where:'current', true %}
{% for student in tstudentB %}
{% if student.type != "PhD" %}
<article class="post">

  <h2>{{ student.name }} ({{ student.type }} student, {{ student.university }})</h2>
  <div class="entry">
    {{ student.content }}
    <hr>
  </div>

</article>
{% endif %}
{% endfor %}
</div>

<hr>

# Previous Students

<hr>

<div class="entry">
{% assign tstudentC = site.students | reverse | where:'current', false %}
{% for student in tstudentC %}
<article class="post">

  <h2>{{ student.name }} ({{ student.type }} student, {{ student.university }})</h2>
  <div class="entry">
    {{ student.content }}
    <hr>
  </div>

</article>
{% endfor %}
</div>
