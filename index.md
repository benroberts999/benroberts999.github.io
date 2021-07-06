---
layout: page
---

<img align="right" width="50%" src="{{ site.baseurl }}/images/ben.jpg" border="250">

**_ARC DECRA Fellow, University of Queensland, Australia._**
Working in theoretical atomic physics and particle astrophysics. Previously at SYRTE, the Observatoire de Paris, France, working on possibilities for dark matter detection using high-precision atomic clocks, and the University of Nevada, Reno, as part of the GPS.DM Collaboration.
PhD in theoretical atomic physics from UNSW, Australia, in Sydney.

### Links
 * ORCiD: [orcid.org/0000-0002-0345-6375](https://orcid.org/0000-0002-0345-6375)
 * arXiv profile (all papers, free downloads): [arxiv.org/a/roberts_b_1](https://arxiv.org/a/roberts_b_1.html)
 * [UQ page](https://researchers.uq.edu.au/researcher/24237)
 * GitHub: [github.com/benroberts999](https://github.com/benroberts999)
 * [Brief CV (pdf)]({{ site.baseurl }}/cv/cv.pdf)
 * [Full publications list (pdf)]({{ site.baseurl }}/cv/publications.pdf)

### Contact me

 * b.roberts [@] uq.edu.au

<div class="posts">
  {% for post in site.posts %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
    </article>
  {% endfor %}
</div>


<div class="posts">
  {% for post in site.posts %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
    </article>
  {% endfor %}
</div>

<!-- {% if page.featured %} -->
