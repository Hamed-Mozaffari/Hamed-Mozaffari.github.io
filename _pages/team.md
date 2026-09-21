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

<div class="team-grid team-grid-rich" markdown="0">
{% if pi_person %}{% include team_card.html member=pi_person %}{% endif %}
{% for member in management %}{% include team_card.html member=member %}{% endfor %}
</div>

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
<span class="team-portrait"><img src="{{ '/images/team/open-position.svg' | relative_url }}" class="team-photo" alt="Open position" width="400" height="500" loading="lazy"></span>
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
