---
title: "Team"
layout: page
permalink: /team/
---

# Team

**We are looking for new team members!**

{% comment %}
  Every person on this page comes from a file in the _people/ folder.
  Add a file there and the person appears here with their own page at
  /team/<file-name>/. Copy _people/_TEMPLATE.md to start a new one.
{% endcomment %}

{% comment %}
  Which section a person appears in is set by `group:` in their file:
    group: management -> next to the PI
    group: staff      -> Staff
    group: students   -> Graduate Students  (also the default if `group` is missing)
  The PI is the one file with `pi: true`.
{% endcomment %}

{% assign pi_person = site.people | where: "pi", true | first %}
{% assign management = site.people | where: "group", "management" | sort: "order" %}
{% assign staff = site.people | where: "group", "staff" | sort: "order" %}
{% assign students = site.people | where_exp: "p", "p.pi != true and p.group != 'staff' and p.group != 'management'" | sort: "order" %}

## PI

<div class="section-card" markdown="0">
<div class="pi-card">
{% if pi_person %}<a href="{{ pi_person.url | relative_url }}"><img src="{{ site.photo | prepend: '/images/' | relative_url }}" class="pi-photo" alt="{{ site.name }}" width="160" height="160"></a>{% else %}<img src="{{ site.photo | prepend: '/images/' | relative_url }}" class="pi-photo" alt="{{ site.name }}" width="160" height="160">{% endif %}
<div>
<h3 class="pi-name">{% if pi_person %}<a href="{{ pi_person.url | relative_url }}">{{ site.name }}</a>{% else %}{{ site.name }}{% endif %}</h3>
<p style="font-style: italic; color: var(--text-secondary);">{{ site.title }}, {{ site.institution }}</p>
<div class="pi-links">
{% if site.email %}<a href="mailto:{{ site.email }}" class="icon-link" title="Email" aria-label="Email">{% include icon.html name="envelope" %}</a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" class="icon-link" title="Google Scholar" aria-label="Google Scholar">{% include icon.html name="google-scholar" %}</a>{% endif %}
{% if site.links.cv and site.links.cv != "" %}<a href="{{ site.links.cv | prepend: '/' | relative_url }}" class="icon-link" title="CV" aria-label="CV">{% include icon.html name="cv" %}</a>{% endif %}
{% if site.links.github and site.links.github != "" %}<a href="{{ site.links.github }}" class="icon-link" title="GitHub" aria-label="GitHub">{% include icon.html name="github" %}</a>{% endif %}
{% if site.links.researchgate and site.links.researchgate != "" %}<a href="{{ site.links.researchgate }}" class="icon-link" title="ResearchGate" aria-label="ResearchGate">{% include icon.html name="researchgate" %}</a>{% endif %}
</div>
{% if site.data.pi[0].education %}
<ul style="margin-top: var(--space-4);">
{% for education in site.data.pi[0].education %}
<li>{{ education | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
{% endif %}
{% if pi_person %}
<p style="margin-top: var(--space-4);"><a href="{{ pi_person.url | relative_url }}">Full profile &rarr;</a></p>
{% endif %}
</div>
</div>
</div>

{% if management.size > 0 %}
<div class="team-grid team-grid-rich" markdown="0">
{% for member in management %}{% include team_card.html member=member %}{% endfor %}
</div>
{% endif %}

{% if staff.size > 0 %}
## Staff

<div class="team-grid team-grid-rich" markdown="0">
{% for member in staff %}{% include team_card.html member=member %}{% endfor %}
</div>
{% endif %}

## Graduate Students

<div class="team-grid team-grid-rich" markdown="0">
{% for member in students %}{% include team_card.html member=member %}{% endfor %}
<div class="team-card team-card-rich">
<img src="{{ '/images/rock.jpg' | relative_url }}" class="team-photo" alt="Open position" width="110" height="110" loading="lazy">
<h3 class="team-name">This could be you!</h3>
<p class="team-info">See openings for more info</p>
</div>
</div>

{% if site.data.alumni and site.data.alumni.size > 0 %}
## Alumni

<div class="section-card">
<table class="alumni-table">
<thead>
<tr><th>Name</th><th>Duration</th><th>Current Position</th></tr>
</thead>
<tbody>
{% for member in site.data.alumni %}
<tr>
<td>{{ member.name }}</td>
<td>{{ member.duration }}</td>
<td>{{ member.info }}</td>
</tr>
{% endfor %}
</tbody>
</table>
</div>
{% endif %}

## Administrative Support

<a href="mailto:exampleemail@gmail.com">Example staff</a> is helping us (and other groups) with administration.
