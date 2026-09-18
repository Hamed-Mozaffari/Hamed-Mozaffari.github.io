---
title: "Projects"
layout: page
permalink: /projects/
---

# Projects

{% if site.data.talks.size > 0 %}
<div class="section-card" markdown="0">
{% for item in site.data.talks %}
  <div style="margin-bottom: var(--space-6);">
    <h3 style="margin-bottom: var(--space-2);">{{ item.title }}</h3>
    {% if item.partners %}<p style="font-style: italic; color: var(--text-secondary); margin-bottom: var(--space-2);">{{ item.partners }}</p>{% endif %}
    <p>{{ item.description }}</p>
  </div>
{% endfor %}
</div>
{% endif %}
