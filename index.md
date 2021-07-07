---
layout: page
---

<img align="right" width="45%" src="{{ site.baseurl }}/images/ben.jpg" border="500">

**_ARC DECRA Fellow, University of Queensland, Australia._**
Working in theoretical atomic physics and particle astrophysics. Previously at
[SYRTE, the Observatoire de Paris](https://syrte.obspm.fr),
France, working on possibilities for dark matter detection using high-precision atomic clocks, and the University of Nevada, Reno, as part of the
[GPS.DM](http://www.dereviankogroup.com/gps-dark-matter/) Collaboration.
[PhD]({{ site.baseurl }}/posts/phd-thesis)
in theoretical atomic physics from UNSW, Australia, in Sydney.

### Links
 * ORCiD: [orcid.org/0000-0002-0345-6375](https://orcid.org/0000-0002-0345-6375)
 * arXiv profile (all papers, free downloads): [arxiv.org/a/roberts_b_1](https://arxiv.org/a/roberts_b_1.html)
 * [UQ researcher page](https://researchers.uq.edu.au/researcher/24237)
 * GitHub: [github.com/benroberts999](https://github.com/benroberts999)
 * [Brief CV (pdf)]({{ site.baseurl }}/cv/cv.pdf)
 * [Full publications list (pdf)]({{ site.baseurl }}/cv/publications.pdf)
 * Contact me: b.roberts [@] uq.edu.au



&nbsp;

*********************************************************************

## Selected publications:

<div class="entry">
{% assign pubs = site.publications | reverse | where:'featured', true %}
{% for pub in pubs limit:6 %}
<article class="post">

  <h1><a href="{{ site.baseurl }}{{ pub.url }}">{{ pub.title }}</a></h1>

  <div class="entry">
    {{ pub.excerpt }}
  </div>

</article>
{% endfor %}
</div>

[See more: /research:]({{ site.baseurl }}/research)

*********************************************************************

## Recent posts:

<div class="entry">
{% assign posts = site.posts | reverse %}
{% for post in posts limit:3 %}
<article class="post">

  <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>

  <div class="entry">
    {{ post.excerpt }}
  </div>

</article>
{% endfor %}
</div>

[See more: /posts:]({{ site.baseurl }}/posts)
