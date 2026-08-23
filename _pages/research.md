---
layout: portfolio
permalink: /research/
title: research
nav: true
nav_order: 1
---
{% assign p = site.data.portfolio %}

<section class="page-hero compact">
  <span class="section-kicker">RESEARCH</span>
  <h1>Engineering the interface between soft materials and living tissue</h1>
  <p>My research connects molecular and polymer design with electrical interfacing, neuromodulation, and tissue regeneration.</p>
</section>

{% for item in p.research %}
<section class="research-detail" id="{{ item.id }}">
  <div class="detail-index">{{ item.number }}</div>
  <div class="detail-copy">
    <h2>{{ item.title }}</h2>
    <p class="detail-lead">{{ item.summary }}</p>
    {% if item.id == 'injectable' %}
    <p>My work on injectable conductive hydrogels focuses on forming electrical interfaces in geometries where conventional patch or cuff electronics are difficult to deploy. The material is designed to conform to tissue, establish conduction in situ, and integrate with soft electronic systems.</p>
    <div class="detail-highlight"><b>Representative contribution</b><span>Injectable tissue prosthesis for instantaneous closed-loop rehabilitation · <i>Nature</i> (2023)</span></div>
    {% elsif item.id == 'neural' %}
    <p>I investigate how adhesion, conductivity, and mechanical compatibility can be combined in biomaterial interfaces for injured nerves. The goal is to stabilize tissue contact while supporting regenerative outcomes rather than treating electrical function and tissue repair as separate design problems.</p>
    <div class="detail-highlight"><b>Representative contribution</b><span>Adhesive and Conductive Fibrous Hydrogel Bandages for Effective Peripheral Nerve Regeneration · <i>Advanced Healthcare Materials</i> (2025)</span></div>
    {% else %}
    <p>I am extending injectable and soft material interfaces toward stimulation systems that can operate with less implanted hardware. Current interests include closed-loop rehabilitation, wireless material-mediated stimulation, and bioelectronic control of regenerative signaling.</p>
    <div class="detail-highlight"><b>Current direction</b><span>Minimally invasive material platforms for local neuromodulation and regenerative biointerfaces.</span></div>
    {% endif %}
  </div>
  <div class="detail-visual graphic-{{ forloop.index }}"><span class="graphic-dot dot-a"></span><span class="graphic-dot dot-b"></span><span class="graphic-line"></span></div>
</section>
{% endfor %}

<section class="vision-section on-page">
  <div class="vision-copy">
    <span class="section-kicker light">{{ p.vision.kicker }}</span>
    <h2>{{ p.vision.title }}</h2>
    <p>{{ p.vision.intro }}</p>
  </div>
  <div class="vision-grid">
    {% for pillar in p.vision.pillars %}
    <div class="vision-item"><span>0{{ forloop.index }}</span><h3>{{ pillar.title }}</h3><p>{{ pillar.text }}</p></div>
    {% endfor %}
  </div>
</section>
