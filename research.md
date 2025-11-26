---
layout: page
title: Research
permalink: /research/
---

Research in theoretical atomic physics and particle astrophysics. My work focusses on high-precision atomic structure calculations, and how atomic processes can be used for testing fundamental theories, probing for physics beyond the standard model, and searching for dark matter.

<div style="border-style:transparent; border-width:250px;">
  <img align="center" width="95%" src="{{site.baseurl}}/images/LesHouches2023-small.jpg">
    <div>
      <span><font size="0.25">  <i>Les Houches, 2023</i></font></span >
    </div>  
</div>
<div style="clear:both"></div>

### Grants

* 2025 - ARC Discovery Project DP250103374: with Dr. Jacinda Ginges (UQ) and Dr. Natalia Oreshkina (MPI)
  * _Nuclear structure and precision tests of fundamental physics in atoms_
* 2023 - Big Questions Institute Fellowship
  * _Are the laws of physics the same everywhere in the universe?_
* 2023 - ARC Discovery Project DP230101685: with Dr. Jacinda Ginges (UQ) and Dr. Magdalena Kowalska (ISOLDE, CERN)
  * _Probing new physics with atomic parity violation_
* 2021 - ARC Early Career Research Award (DECRA) DE210101026
  * _Atomic physics as a probe for fundamental physics and dark matter_

### Links

* [Brief CV (pdf)]({{ site.baseurl }}/docs/cv-RobertsBM.pdf)
* [Full publications list (pdf)]({{ site.baseurl }}/docs/publications-RobertsBM.pdf)
  <!-- * [Publications with abstracts]({{ site.baseurl }}/docs/publications-Abstracts-RobertsBM.pdf) -->
  * ORCiD: [orcid.org/0000-0002-0345-6375](https://orcid.org/0000-0002-0345-6375)
  * arXiv profile (all papers, free downloads): [arxiv.org/a/roberts_b_1](https://arxiv.org/a/roberts_b_1.html)
  * [Google Scholar profile](https://scholar.google.com.au/citations?user=5i5bTuwAAAAJ)
  * [InspireHEP: B.M.Roberts.1](http://inspirehep.net/author/profile/B.M.Roberts.1)
  * [ADS publications page](https://ui.adsabs.harvard.edu/public-libraries/vWzKbWxgTBqzF8vVh78nAQ)
* [UQ page](https://researchers.uq.edu.au/researcher/24237)
* [Recent slides/presentations]({{ site.baseurl }}/slides)

<!-- Slides from most of my recent conference presentations can be found [here]({{ site.baseurl }}/talks) -->

## Recent publications

 {% for pub in site.publications reversed %}
 <article class="post">

   <h1><a href="{{ site.baseurl }}{{ pub.url }}">{{ pub.title }}</a></h1>
   <div class="entry">
     {{ pub.excerpt }}
     <br>
   </div>

 </article>
 {% endfor %}
