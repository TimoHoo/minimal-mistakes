---
permalink: /Arkisto/
title: "Arkisto vuosittain"
layout: archive
excerpt: "Tämä on arkisto vuosittaisia posteja ja viestejä varten."
sitemap: true
author_profile: false

modified: 2016-11-30
---
{% include base_path %}
{% capture written_year %}'None'{% endcapture %}

{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
   <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
   {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}