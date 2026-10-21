---
layout: page
title: Research
stitle: Research
permalink: /projects/
description:
nav: true
nav_order: 1
sections:
  - title: Hybrid Learning
    projects: [hybrid-learning]
  - title: Robotics
    projects: [eeg]
  - divider: Selected Past Projects
  - title: Communication-Aware Control
    note: Funded by the Swedish Foundation for Strategic Research (SSF) and Ericsson AB.
    projects: [camp]
  - title: Intelligent Transportation
    projects: [itsc21]
  - title: Swarm Dynamics
    projects: [tcns22]
---

<div class="projects">

{%- for section in page.sections -%}
  {%- if section.divider -%}
    <h2 class="category category-divider">{{ section.divider }}</h2>
  {%- else -%}
    <h2 class="category">{{ section.title }}</h2>
    {%- if section.note %}<p class="category-note">{{ section.note }}</p>{% endif -%}
    <div class="container">
      <div class="row row-cols-0">
        {%- for slug in section.projects -%}
          {%- assign project = site.projects | where: "slug", slug | first -%}
          {% include project_card.liquid %}
        {%- endfor %}
      </div>
    </div>
  {%- endif -%}
{%- endfor %}

</div>
