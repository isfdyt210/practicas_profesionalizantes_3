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
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.url + "hola" }}</a>
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
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
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
          <a class="post-link" href="{{ ppt.path | prepend: site.baseurl }}">{{ ppt.basename }}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>



</div>
