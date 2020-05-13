---
layout: default
---

<div class="home">

  <h1 class="page-heading">Novedades</h1>

  <ul class="post-list">
    {% for post in site.posts %}
      {% if post.categories contains "articles" %}
      <li>
        <span class="post-meta">{{ post.date | date: "%Y/%m/%d " }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
            {{ post.title }}
          </a>
        </h2>
      </li>
      {% endif %}
    {% endfor %}
  </ul>

  <h1 class="page-heading">Clases</h1>

  <ul class="post-list">
    {% for post in site.posts %}
      {% if post.categories contains "courses" %}
      <li>
        <span class="post-meta">{{ post.date | date: "%Y/%m/%d " }}</span>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
            {{ post.title }}
          </a>
        </h2>
      </li>
      {% endif %}
    {% endfor %}
  </ul>

  <h1 class="page-heading">Presentaciones</h1>

  <ul class="post-list">
    {% assign ppt_files = site.static_files | where: "presentation", true %}
    {% for ppt in ppt_files %}
      <li>
        <h2>
          <a class="post-link" href="{{ ppt.path | prepend: site.baseurl }}">
            {{ ppt.basename | replace:'.',' ' | capitalize }}
          </a>
        </h2>
      </li>
    {% endfor %}
  </ul>

  <h1 class="page-heading">Explicaciones Teóricas</h1>
  <ul class="post-list">
    {% for teory in site.data.teories %}
      <li>
        <a class="post-link" href="{{ teory.url }}">
          {{ teory.name }}
        </a>
      </li>
    {% endfor %}
  </ul>

  <h1 class="page-heading">Practicas</h1>

  <ul class="post-list">
    {% assign exe_files = site.static_files | where: "exercise", true %}
    {% for exe in exe_files %}
      <li>
        <h2>
          <a class="post-link" href="{{ exe.path | prepend: site.baseurl }}">
            {{ exe.basename | replace:'.',' ' | capitalize }}
          </a>
        </h2>
      </li>
    {% endfor %}
  </ul>



</div>
