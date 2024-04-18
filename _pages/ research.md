---
layout: page
title: research
permalink: /research/
description: A growing collection of my research projects.
nav: true
# nav_order: 2
display_categories: [Optimization+AMoD, MARL+AMoD, Robust+MARL]
horizontal: false
---

<h3>Background</h3>
<p>In this era of digital transformation and embedded sensors, Cyber-Physical Systems (CPS) are playing an increasingly prominent role in industries ranging from transportation to energy and manufacturing. These systems typically involve the tight integration between distributed computational intelligence, communication networks, and the physical world. Their performance and efficiency largely depend on the collaborative efforts of individual entities in the system. In this context, it is important not only to make individual devices smarter, but also to make whole interconnected systems collectively intelligent by complex interaction modeling, cooperative decision-making, self-organization, and human-machine interactivity. For instance, in smart transportation systems, vehicles are no longer mere solitary entities; they make collaborative decisions based on data from surrounding vehicles to prevent collisions or optimize traffic flow. However, due to the increasing model complexity, ever-changing external environments, unpredictable internal dynamics, and high expectations of Collective Intelligence, highly interconnected and integrated CPS pose new challenges and concerns about efficiency, robustness, safety, and security.</p>

<h3>Research Theme I: Robust multi-agent reinforcement learning (MARL) for interconnected CPS</h3>
<p>From uncertain sensing to security risks, from the demands of real-time decisions to coordinating numerous entities, every step contains inherent complexities in interconnected CPS. MARL presents a potential to optimize the collective intelligence of interconnected CPS, due to its ability to handle decentralized decision-making processes, adaptability in dynamic environments, and capacity to leverage shared experiences among agents. However, in real-world applications, the agent may face state uncertainty that may be caused by unavoidable sensor measurement errors, noise, missing information, communication issues, and/or malicious attacks, and suffer from model uncertainty that usually results from the simulation-to-reality gap. These uncertainties pose significant challenges to the efficacy and reliability of MARL algorithms and the complexity of interactions among agents amplifies these uncertainties. It is significant and challenging to develop robust MARL to handle these uncertainties to ensure the performance and reliability of interconnected CPS. My contributions to this theme are:</p>
<ul>
    <li>Foundations for robust MARL under uncertainty including problem formulations, solution concepts, theoretical analysis, and performance-guaranteed algorithm designs</li>
    <li>Practical robust MARL frameworks and algorithms under state and model uncertainties for autonomous mobility-on-demand systems with real-world constraints</li>
    <li>Significant improvement in different metrics (energy, fairness, profit) in interconnected CPS</li>
</ul>

**See the following projects about applications and theories of Robust MARL**
<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  {%- if category == "MARL+AMoD" or category == "Robust+MARL"%}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <!-- <div class="grid"> -->
    {%- for project in sorted_projects -%}
      <div class="thumbnail">
      <h4>{{ project.title }}</h4>
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <br/>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
    {%- endfor %}
    {%- endif -%}
  <!-- </div> -->
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      <div class="thumbnail">
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h4>{{ project.title }}</h4>
            <br/>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>

<br> 
<br> 

<h3>Research Theme II: Data-driven distributionally robust optimization (DRO) for mobile CPS</h3>
<p>With the transformation to smarter cities and the development of autonomous vehicle technologies, transportation services provided by mobile CPS (e.g., ride-sharing systems, electric autonomous vehicles, mobility-on-demand systems, bike sharing, and e-scooter sharing systems) have begun to reshape the urban landscape in unprecedented ways. The integration of these services into our daily lives has not only reduced traffic congestion, decreased carbon emissions, and boosted environmental sustainability, but has posed challenges to the traditional dynamics of urban planning and transportation control. For example, how to capture the complexity and analyze the dynamic interplay between urban-scale phenomena from data (such as demand and supply of transportation systems), and take actions to improve service efficiency, system robustness, and fairness, is still a challenging problem. My contributions to this theme include:</p>
<ul>
    <li>Integrated algorithm design of model prediction and distributionally robust optimization, where future mobility demand and supply are predicted based on large-scale historical data and real-time data</li>
    <li>Demand and supply prediction uncertainty sets construction algorithms with performance guarantee</li>
    <li>Significant reduction of the total idle distance of all vehicles to satisfy mobility demand</li>
    <li>Improvement of EV charging services fairness, mobility services fairness, and profit fairness</li>
</ul>

**See the following projects about applications and theories of Distributionally Robust Optimization**

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  {%- if category == "Optimization+AMoD" %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <!-- <div class="grid"> -->
    {%- for project in sorted_projects -%}
      <div class="thumbnail">
      <h4>{{ project.title }}</h4>
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <br/>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
    {%- endfor %}
    {%- endif -%}
  <!-- </div> -->
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      <div class="thumbnail">
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h4>{{ project.title }}</h4>
            <br/>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>