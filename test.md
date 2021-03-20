--- 
layout: default 
title: Home 
permalink: /test/ 
category: home 
---

<header class="page-header {% if page.background-photo %}{{ page.background-photo }}{% else %}cabbage-background{% endif %} ds-u-padding-y--6">
  <div class="ds-l-container">
    <div class="ds-l-row">
      <h1 class="ds-display ds-u-padding-x--2">{{ page.title | escape }}</h1>
    </div>
  </div>
</header>

<section class="ds-l-container preview__grid">
  <div class="ds-l-row">
    <article class="ds-l-col--8 ds-u-margin-top--7">
      {{ content }}
    </article>

    <aside class="ds-l-col--4">
      <nav class="page-navigation ds-u-margin-top--7">
      {% for item in site.data.navigation %}
        {% for entry in item.sublinks %}
          {% if entry.url == page.url %}
          <div class="page-navigation-title ds-u-padding--1">
            {{item.title}}
          </div>
          <ul class="ds-c-list--bare ds-u-padding--1">
            {% for entry in item.sublinks %}
              <li class="ds-u-padding--1"><a href="{{entry.url}}">{{entry.title}}</a</li>
            {% endfor %}
          </ul>
          {% endif %}
        {% endfor %}
      {% endfor %}
      </nav>
    </aside>
  </div>
</section>
