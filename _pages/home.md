---
title: "Home"
layout: homelay
permalink: /
---

<h1 class="home-hero">{{ site.lab_name | default: site.name }}</h1>
<p class="home-hero-sub">{{ site.lab_full }}</p>

<div class="chip-container" markdown="0">
<a href="{{ '/research' | relative_url }}" class="chip">Artificial Intelligence</a>
<a href="{{ '/research' | relative_url }}" class="chip">Computer Vision</a>
<a href="{{ '/research' | relative_url }}" class="chip">Remote Sensing</a>
<a href="{{ '/research' | relative_url }}" class="chip">Robotics &amp; Automation</a>
<a href="{{ '/research' | relative_url }}" class="chip">Internet of Things</a>
<a href="{{ '/research' | relative_url }}" class="chip">Digital Twins &amp; BIM</a>
</div>

{{ site.lab_name }} applies artificial intelligence, computer vision, and remote sensing to the built environment.
Working with the Industrialized and Digitalized Construction team at the National Research Council Canada, we develop tools that make construction safer, faster, and more precise — from autonomous drones that inspect confined structures, to cloud-based models that monitor infrastructure and detect wildfire risk across large landscapes.
The common thread is turning visual and sensor data into decisions that engineers can act on.

<div class="callout callout-success" markdown="0">
<div class="callout-title">{% include icon.html name="award" class="callout-icon" %} Director General Innovation Award, 2022</div>
<p>Recognized by the National Research Council Canada for contributions to the AI4L project, applying artificial intelligence and emerging technology to improve safety in Canadian transportation.</p>
</div>

<div class="banner-frame" markdown="0">
<img src="{{ '/images/artificial.jpeg' | relative_url }}" alt="Artificial intelligence and computer vision applied to the built environment" width="1400" height="449" loading="lazy">
<div class="banner-caption">Artificial intelligence and computer vision for the built environment.</div>
</div>

## What we work on

Our work spans modular, prefabricated, and on-site construction, and brings together six threads: deep learning and large language models for prediction and document analysis; computer vision for detection, segmentation, and thermal inspection; satellite, drone, and hyperspectral imagery for large-area monitoring; autonomous robots and UAV platforms for surveying and quality control; connected sensors for continuous condition monitoring; and digital twins that keep a building's model in step with the building itself.

<p><a href="{{ '/research' | relative_url }}">Explore our research areas &rarr;</a></p>

{% capture selected %}{% bibliography --query @*[selected=true] %}{% endcapture %}
{% if selected contains "pub-entry" %}
## Selected publications

<div class="section-card selected-pubs" markdown="0">
{{ selected }}
<p style="margin: var(--space-4) 0 0;"><a href="{{ '/publications' | relative_url }}">All publications &rarr;</a></p>
</div>
{% endif %}

## The team

{% assign pi_person = site.people | where: "pi", true | first %}
The lab is led by {% if pi_person %}<a href="{{ pi_person.url | relative_url }}">{{ site.name }}</a>{% else %}{{ site.name }}{% endif %}, {{ site.title }} at the Construction Research Centre, National Research Council Canada, Status-Only Assistant Professor in Mechanical and Industrial Engineering at the University of Toronto, and a part-time lecturer at Carleton University.

<p><a href="{{ '/team' | relative_url }}">Meet the team &rarr;</a></p>

## Join us

We are looking for new team members. If you work on artificial intelligence, computer vision, remote sensing, or robotics for the built environment and want to collaborate, <a href="mailto:{{ site.email }}">get in touch</a>.
