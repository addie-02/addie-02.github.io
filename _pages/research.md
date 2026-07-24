---
title: "Research"
layout: archive
permalink: /research/
---

## Projects
---
<div class="project-entry">
  <div class="project-media">
    <img src="{{ site.baseurl }}/images/projects/bee_abm_animation_orchard.gif" alt="Bee ABM simulation output">
  </div>
  <div class="project-text">
    <h3>Bee Foraging Agent-Based Model (WIP)</h3>
    <p>A on-lattice agent-based model of bee foraging behaviour, incorporating flower pollination dynamics, waggle-dance-style recruitment, and Q-learning for adaptive foraging strategy. Implemented in Python.</p>
    <p><a href="https://github.com/addie-02/bee-foraging-abm" target="_blank">View repository →</a></p>
  </div>
</div>

<div class="project-entry">
  <div class="project-media">
    <img src="{{ site.baseurl }}/images/projects/predictions.jpg" alt="FDA electricity demand forecast">
  </div>
  <div class="project-text">
    <h3>National Grid: Function-on-Function Electricity Demand Forecasting (WIP)</h3>
    <p>SAMBa ITT24 project modelling UK electricity demand via function-on-function regression (<code>pffr()</code>, R), with functional covariates for lagged demand, temperature, wind speed, and activity profiles across          five UK cities. Post-modelling analysis included FPCA and covariance surface visualisation.</p>
    <p><a href="https://github.com/addie-02/ITT24-FDA-NGED" target="_blank">View repository →</a></p>
  </div>
</div>

<div class="project-entry">
  <div class="project-media">
    <img src="{{ site.baseurl }}/images/projects/derby_predictions-21.pdf" alt="FDA electricity demand forecast">
  </div> 
  <div class="project-entry">
    <h3>Adaptive Therapy: Resistance Formation Modelling</h3>
    <p>Extension of a Lotka-Volterra competition model (Gallagher et al., 2025) with a drug-concentration-dependent resistance formation function λ(D; c), PK drug decay, and bactericidal death rates, comparing constant,           adaptive, and threshold dosing regimes.</p>
    <p><a href="https://github.com/addie-02/" target="_blank">View repository →</a></p>
  </div>
</div>



## Papers
---

{% for pub in site.publications reversed %}
  <div class="paper-entry">
    <h3>{{ pub.title }}</h3>
    <p><em>{{ pub.venue }}</em>, {{ pub.date | date: "%Y" }}</p>
    <p>{{ pub.excerpt }}</p>
    <p><a href="{{ pub.paperurl }}" target="_blank">Full paper →</a></p>
  </div>
{% endfor %}

{% if site.publications.size == 0 %}
  <p><em>No papers published yet — check back soon!</em></p>
{% endif %}
