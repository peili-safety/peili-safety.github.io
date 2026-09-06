---
layout: default
title: Papers
permalink: /publications/
section: papers
redirect_from:
  - /papers/
---
<h1 class="title">Papers</h1>
<p class="smallhead section-intro mt-3">Journal articles, conference papers, and preprints. See also <a href="{{ site.author.googlescholar }}">Google Scholar</a>.</p>
<nav class="section-links" aria-label="Publication years">{% assign years = site.data.publications | group_by: 'year' %}{% for year in years %}<a href="#year-{{ year.name }}">{{ year.name }}</a>{% endfor %}</nav>
{% for year in years %}
<section aria-labelledby="year-{{ year.name }}">
  <h2 class="head paper-year" id="year-{{ year.name }}"><span id="{{ year.name }}">{{ year.name }}</span></h2>
  <div class="row">
  {% for paper in year.items %}
    <article class="col-md-6 col-lg-4 paperbox">
      <div class="paper-list-entry">
        <div class="paper-list-text">
          <h3 class="smallhead"><a class="off" href="{{ paper.page_url | relative_url }}">{{ paper.title }}</a></h3>
          <p class="paper-short-citation">{{ paper.short_citation }}</p>
        </div>
        {% if paper.figure %}<a class="paper-thumbnail" href="{{ paper.page_url | relative_url }}" aria-label="View {{ paper.title | escape }}"><img src="{{ paper.figure | relative_url }}" alt="{{ paper.figure_alt | escape }}" width="100" height="100" loading="lazy"></a>{% endif %}
      </div>
    </article>
  {% endfor %}
  </div>
</section>
{% endfor %}
