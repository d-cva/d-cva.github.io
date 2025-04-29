---
layout: default
title: "Blog"
---

{% if site.show_excerpts %}
  {% include index.md %}
{% else %}
  {% include archive.html title="Labs" %}
{% endif %}
