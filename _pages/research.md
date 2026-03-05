---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}



{% for post in site.work reversed %}
  {% include archive-single.html %}
{% endfor %}