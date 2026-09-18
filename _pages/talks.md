---
title: "Projects"
layout: page
permalink: /project/
---

# Projects

<div class="research-grid">
{% for item in site.data.talks %}
<div class="research-card">
{% if item.image %}<img src="{{ item.image | prepend: '/images/projects/' | relative_url }}" class="research-thumb" width="400" height="200" alt="{{ item.title }}">{% endif %}
<div class="research-body">
<h2 class="research-title">{{ item.title }}</h2>
{% if item.partners %}<p style="font-style: italic; color: var(--text-secondary); margin-bottom: var(--space-3);">{{ item.partners }}</p>{% endif %}
<p class="research-desc">{{ item.description }}</p>
</div>
</div>
{% endfor %}
</div>
