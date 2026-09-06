---
layout: default
permalink: /
title: Pei Li research group
section: home
redirect_from:
  - /about/
  - /about.html
---
<section class="home-intro" aria-labelledby="home-title">
  <p class="eyebrow">UNIVERSITY OF WYOMING</p>
  <h1 class="bigtitle" id="home-title">Pei Li research group</h1>
  <div class="smallhead">
    <p>We work at the intersection of transportation science, multimodal and generative AI, and statistical learning. We study how transportation systems can be understood, predicted, and represented from heterogeneous observations, and how transportation knowledge can improve the reliability of AI models.</p>
    <p>Our research spans <a href="{{ '/portfolio/#safety' | relative_url }}">transportation safety</a>, <a href="{{ '/portfolio/#multimodal' | relative_url }}">multimodal AI and reasoning</a>, and <a href="{{ '/portfolio/#twins' | relative_url }}">digital twins and cooperative mobility</a>.</p>
  </div>
  <p class="note mt-4"><a href="{{ '/lab/#available-positions' | relative_url }}">We are recruiting MS and PhD students →</a></p>
</section>
<section class="home-section" id="news" aria-labelledby="recent-news">
  <h2 class="head" id="recent-news"><a class="off" href="{{ '/news/' | relative_url }}">Recent news</a></h2>
  <div class="row">
  {% for item in site.data.news limit:4 %}
    {% assign fallback_url = '/news/#' | append: item.id %}
    <article class="col-md-6 col-lg-3 home-item"><div class="note"><i class="fa-regular fa-comment fa-fw" aria-hidden="true"></i> <a class="off" href="{{ item.url | default: fallback_url | relative_url }}">{{ item.title }}</a></div><div class="smallnote">{{ item.date | append: '-01' | date: '%B %Y' }}</div></article>
  {% endfor %}
  </div>
</section>
<section class="home-section" aria-labelledby="recent-papers">
  <h2 class="head" id="recent-papers"><a class="off" href="{{ '/publications/' | relative_url }}">Recent papers</a></h2>
  <div class="row">
  {% for paper in site.data.publications limit:4 %}
    <article class="col-md-6 col-lg-3 home-item"><div class="note"><i class="fa-regular fa-file-lines fa-fw" aria-hidden="true"></i> <a class="off" href="{{ paper.page_url | relative_url }}">{{ paper.title }}</a></div><div class="smallnote">{{ paper.venue | markdownify | remove: '<p>' | remove: '</p>' }} · {{ paper.year }}</div></article>
  {% endfor %}
  </div>
</section>
<section class="home-section" aria-labelledby="current-projects">
  <h2 class="head" id="current-projects"><a class="off" href="{{ '/portfolio/#research-projects' | relative_url }}">Research projects</a></h2>
  <div class="row">
  {% for project in site.data.research.projects limit:4 %}
    {% assign project_anchor = project.title | slugify %}
    {% assign fallback_url = '/portfolio/#' | append: project_anchor %}
    <article class="col-md-6 col-lg-3 home-item"><div class="note"><i class="fa-regular fa-pen-to-square fa-fw" aria-hidden="true"></i> <a class="off" href="{{ project.url | default: fallback_url | relative_url }}">{{ project.title }}</a></div><div class="smallnote">{{ project.period }} · {{ project.status }}</div></article>
  {% endfor %}
  </div>
</section>
