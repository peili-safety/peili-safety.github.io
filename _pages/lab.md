---
layout: default
title: Team
permalink: /lab/
section: team
redirect_from:
  - /lab-team
  - /team/
---
<h1 class="title">Team</h1>
<p class="smallhead section-intro mt-3">Our group studies transportation safety, multimodal AI, and digital twins in the Department of Civil and Architectural Engineering and Construction Management at the University of Wyoming.</p>
<nav class="section-links" aria-label="Team sections"><a href="#lab-members">Current members</a><a href="#available-positions">Join the group</a><a href="#funding-and-awards">Awards</a></nav>
<section id="lab-members" aria-labelledby="members-heading">
<h2 class="head section-title" id="members-heading">Current members</h2>
<div class="row">
{% for person in site.data.people %}
<article class="col-lg-6"{% if forloop.first %} id="lab-director"{% endif %}>
  <div class="media memberbox">
    {% if person.image %}<a href="{{ person.website | relative_url }}"><img class="member-photo" src="{{ person.image | relative_url }}" alt="{{ person.name }}" width="150" height="180"></a>{% else %}<div class="member-photo member-placeholder" role="img" aria-label="Photo forthcoming for {{ person.name }}"><span class="initials" aria-hidden="true">{{ person.initials }}</span><span aria-hidden="true">Photo forthcoming</span></div>{% endif %}
    <div class="media-body">
      <h3 class="head">{% if person.website %}<a class="off" href="{{ person.website | relative_url }}">{{ person.name }}</a>{% else %}{{ person.name }}{% endif %}</h3>
      <p class="member-role">{{ person.role }}</p>
      <p><a href="mailto:{{ person.email }}">{{ person.email }}</a></p>
      <div class="member-links note">{% if person.website %}<a href="{{ person.website | relative_url }}">Profile</a>{% endif %}{% if person.scholar %}<a href="{{ person.scholar }}">Google Scholar</a>{% endif %}</div>
    </div>
  </div>
</article>
{% endfor %}
</div>
</section>
<section id="available-positions" class="reading-column" aria-labelledby="join-heading">
<h2 class="head section-title" id="join-heading">Join the group</h2>
<div class="page-content"><p>We welcome motivated students interested in transportation and AI. The lab has openings at the MS and PhD levels.</p><p>Read the position posting for detailed requirements, and contact Pei Li to discuss your interests and opportunities in the group.</p></div>
<p class="note"><a href="{{ '/files/position_post.pdf' | relative_url }}">View position posting (PDF)</a> · <a href="mailto:pei.li@uwyo.edu">Contact Pei Li</a></p>
</section>
<section id="funding-and-awards" class="reading-column" aria-labelledby="awards-heading">
<h2 class="head section-title" id="awards-heading">Research support and awards</h2>
<div class="page-content"><p>Our <a href="{{ '/portfolio/#research-projects' | relative_url }}">Research page</a> describes funded projects, sponsors, and completed studies.</p>
<ul><li><strong>UW Data Science Faculty Fellow (2026–2027)</strong> — Supported by the UW Data Science Center to advance real-time roadway safety monitoring using vehicle telematics.</li><li><strong>Roger Wilmot Memorial Fund Travel Grant (2026)</strong> — Supporting TRB 2027 participation and research exchange on AI-enabled rural transportation safety.</li></ul></div>
</section>
