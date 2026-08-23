---
layout: portfolio
permalink: /
title: home
nav: false
---
{% assign p = site.data.portfolio %}

<section class="hero-section">
  <div class="hero-copy">
    <div class="eyebrow">{{ p.hero.eyebrow }}</div>
    <h1>{{ p.hero.headline }}</h1>
    <p class="hero-sub">{{ p.hero.subheadline }}</p>
    <div class="hero-actions">
      <a class="btn btn-primary" href="{{ p.hero.primary_url | relative_url }}">{{ p.hero.primary_cta }} <span>→</span></a>
      <a class="btn btn-ghost" href="{{ p.hero.secondary_url | relative_url }}">{{ p.hero.secondary_cta }}</a>
    </div>
  </div>

  <div class="hero-visual" aria-label="Research pathway from injectable materials to regenerative outcomes">
    <div class="visual-orbit orbit-a"></div>
    <div class="visual-orbit orbit-b"></div>
    <div class="visual-core"><span>soft<br>interface</span></div>
    <div class="visual-node node-1"><span class="node-index">01</span><b>Inject</b><small>material delivery</small></div>
    <div class="visual-node node-2"><span class="node-index">02</span><b>Interface</b><small>electrical coupling</small></div>
    <div class="visual-node node-3"><span class="node-index">03</span><b>Stimulate</b><small>neuromodulation</small></div>
    <div class="visual-node node-4"><span class="node-index">04</span><b>Regenerate</b><small>functional recovery</small></div>
  </div>
</section>

<section class="credential-strip" aria-label="Selected credentials">
{% for item in p.credentials %}
  <div class="credential">
    <strong>{{ item.top }}</strong>
    <span>{{ item.bottom }}</span>
  </div>
{% endfor %}
</section>

<section class="section-block" id="research">
  <div class="section-heading">
    <div>
      <span class="section-kicker">SELECTED RESEARCH</span>
      <h2>Material platforms built around the tissue interface</h2>
    </div>
    <a class="text-link" href="{{ '/research/' | relative_url }}">All research →</a>
  </div>

  <div class="research-grid">
  {% for item in p.research %}
    <a class="research-card" href="{{ '/research/#' | append: item.id | relative_url }}">
      <div class="card-top"><span>{{ item.number }}</span><span>↗</span></div>
      <div class="card-graphic graphic-{{ forloop.index }}">
        <span class="graphic-dot dot-a"></span><span class="graphic-dot dot-b"></span><span class="graphic-line"></span>
      </div>
      <h3>{{ item.title }}</h3>
      <p>{{ item.summary }}</p>
      <div class="tag-row">{% for tag in item.tags %}<span>{{ tag }}</span>{% endfor %}</div>
    </a>
  {% endfor %}
  </div>
</section>

<section class="section-block selected-work">
  <div class="section-heading">
    <div>
      <span class="section-kicker">SELECTED WORK</span>
      <h2>Representative publications</h2>
    </div>
    <a class="text-link" href="{{ '/publications/' | relative_url }}">Full publication list →</a>
  </div>

  <div class="work-list">
  {% for work in p.selected_work %}
    <a class="work-item" href="{{ work.url }}" target="_blank" rel="noopener">
      <div class="work-meta"><b>{{ work.journal }}</b><span>{{ work.year }}</span><span>{{ work.role }}</span></div>
      <div class="work-main"><h3>{{ work.title }}</h3><p>{{ work.blurb }}</p></div>
      <div class="work-arrow">↗</div>
    </a>
  {% endfor %}
  </div>
</section>

<section class="vision-section">
  <div class="vision-copy">
    <span class="section-kicker light">{{ p.vision.kicker }}</span>
    <h2>{{ p.vision.title }}</h2>
    <p>{{ p.vision.intro }}</p>
  </div>
  <div class="vision-grid">
  {% for pillar in p.vision.pillars %}
    <div class="vision-item">
      <span>0{{ forloop.index }}</span>
      <h3>{{ pillar.title }}</h3>
      <p>{{ pillar.text }}</p>
    </div>
  {% endfor %}
  </div>
</section>

<section class="closing-cta">
  <span class="section-kicker">POSTDOCTORAL RESEARCH</span>
  <h2>Building the next generation of minimally invasive bioelectronic interfaces.</h2>
  <div class="hero-actions">
    <a class="btn btn-primary" href="{{ '/about/' | relative_url }}">About & contact <span>→</span></a>
    <a class="btn btn-ghost" href="{{ '/cv/' | relative_url }}">View CV</a>
  </div>
</section>
