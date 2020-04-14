---
title:
layout: archive
permalink: /
author_profile: true
comments: false
---

<ul>
  <h1>Recent Posts</h1>
  {% capture written_year %}'None'{% endcapture %}
  {% for post in site.posts %}
    {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
    {% if year != written_year %}
      {% if written_year != "'None'" %}<br>{% endif %}
      <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
      {% capture written_year %}{{ year }}{% endcapture %}
    {% endif %}
    {% include archive-single.html %}
  {% endfor %}
</ul>
