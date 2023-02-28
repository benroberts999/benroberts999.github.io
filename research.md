---
layout: page
title: Research
permalink: /research/
---

Research in theoretical atomic physics and particle astrophysics. My work focusses on high-precision atomic structure calculations, and how atomic processes can be used for testing fundamental theories, probing for physics beyond the standard model, and searching for dark matter.

### Available projects at UQ (honours, PhD)

* Atomic physics as a probe of the Standard Model at low energies
* Development of high-precision atomic structure methods
* Dark matter direct detection via atomic ionisation
* For more details, see: [https://researchers.uq.edu.au/researcher/24237](https://researchers.uq.edu.au/researcher/24237)
* Projects are flexible and other projects are available, contact me with any questions

### Links

* ORCiD: [orcid.org/0000-0002-0345-6375](https://orcid.org/0000-0002-0345-6375)
* arXiv profile (all papers, free downloads): [arxiv.org/a/roberts_b_1](https://arxiv.org/a/roberts_b_1.html)
* [Google Scholar profile](https://scholar.google.com.au/citations?user=5i5bTuwAAAAJ)
* [InspireHEP: B.M.Roberts.1](http://inspirehep.net/author/profile/B.M.Roberts.1)
* [ADS publications page](https://ui.adsabs.harvard.edu/public-libraries/vWzKbWxgTBqzF8vVh78nAQ)
* [UQ page](https://researchers.uq.edu.au/researcher/24237)
* [Brief CV (pdf)]({{ site.baseurl }}/docs/cv-RobertsBM.pdf)
* [Full publications list (pdf)]({{ site.baseurl }}/docs/publications-RobertsBM.pdf)
* [Recent slides/presentations]({{ site.baseurl }}/talks)

<!-- Slides from most of my recent conference presentations can be found [here]({{ site.baseurl }}/talks) -->

## Recent publications

 {% for pub in site.publications reversed %}
 <article class="post">

   <h1><a href="{{ site.baseurl }}{{ pub.url }}">{{ pub.title }}</a></h1>
   <div class="entry">
     {{ pub.excerpt }}
   </div>

 </article>
 {% endfor %}
