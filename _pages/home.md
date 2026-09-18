---
title: "Home"
layout: homelay
permalink: /
---

<h1 class="home-hero">{{ site.name }}</h1>
<p class="home-hero-sub">{{ site.title }}, {{ site.institution }}</p>

<div class="chip-container" markdown="0">
<a href="{{ '/research' | relative_url }}" class="chip">Artificial Intelligence</a>
<a href="{{ '/research' | relative_url }}" class="chip">Computer Vision</a>
<a href="{{ '/research' | relative_url }}" class="chip">Remote Sensing</a>
<a href="{{ '/research' | relative_url }}" class="chip">Robotics &amp; Automation</a>
<a href="{{ '/research' | relative_url }}" class="chip">Internet of Things</a>
<a href="{{ '/research' | relative_url }}" class="chip">Digital Twins &amp; BIM</a>
</div>

My research applies artificial intelligence, computer vision, and remote sensing to the built environment.
Working with the Industrialized and Digitalized Construction team at the National Research Council Canada, I develop tools that make construction safer, faster, and more precise — from autonomous drones that inspect confined structures, to cloud-based models that monitor infrastructure and detect wildfire risk across large landscapes.
The common thread is turning visual and sensor data into decisions that engineers can act on.

<div class="callout callout-success" markdown="0">
<div class="callout-title">{% include icon.html name="award" class="callout-icon" %} Director General Innovation Award, 2022</div>
<p>Recognized by the National Research Council Canada for contributions to the AI4L project, applying artificial intelligence and emerging technology to improve safety in Canadian transportation.</p>
</div>

<div class="banner-frame" markdown="0">
<img src="{{ '/images/banner.webp' | relative_url }}" alt="Research banner" width="1400" height="449" loading="lazy">
<div class="banner-caption">Add your own caption here.</div>
</div>

{% capture selected %}{% bibliography --query @*[selected=true] %}{% endcapture %}
{% if selected contains "pub-entry" %}
## Selected publications

<div class="section-card selected-pubs" markdown="0">
{{ selected }}
<p style="margin: var(--space-4) 0 0;"><a href="{{ '/publications' | relative_url }}">All publications &rarr;</a></p>
</div>
{% endif %}

## About me

I am a Research Officer at the Construction Research Centre, National Research Council Canada, where I work on artificial intelligence, robotics, remote sensing, and IoT for modular, prefabricated, and on-site construction.
I hold a Ph.D. in Electrical Engineering and Computer Science from the University of Ottawa, with a specialization in artificial intelligence and computer vision.
Alongside my research, I am a Status-Only Assistant Professor in Mechanical and Industrial Engineering at the University of Toronto and a part-time lecturer at Carleton University, where I teach remote sensing technologies.
I am a licensed Professional Engineer, a Senior Member of IEEE, a certified thermographer, and an advanced UAV pilot.
