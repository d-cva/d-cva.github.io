---
layout: default
title: "page"
---

{% if site.show_excerpts %}
  {% include index.md %}
{% else %}
  {% include archive.html title="labs" %}
{% endif %}
