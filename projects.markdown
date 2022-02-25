---
layout: default
title: Projects
permalink: /projects/
---

<h1>Projects</h1>

{% for proj in site.projects reversed %}
  {% capture base_image_path %}/assets/images{{ proj.url }}{% endcapture %}
  {% capture thumbnail_basename %}{{ proj.images | first | replace: ".png", "" }}{% endcapture %}
  <article class="project-block">
    <a class="project-link" href="{{ proj.url }}">
      <span>Open</span>
    </a>
    <a class="project-thumbnail" href="{{ proj.url }}">
      <img
        class="thumbnail"
        alt="{{ proj.title }}"
        srcset="{{ base_image_path }}/{{ thumbnail_basename }}-thumb-1x.png 1x,
                {{ base_image_path }}/{{ thumbnail_basename }}-thumb-2x.png 2x"
        src="{{ base_image_path }}/{{ thumbnail_basename }}-thumb-2x.png"
      >
    </a>
    <a class="project-title" href="{{ proj.url }}">
      <h2>{{ proj.title }}</h2>
      <p>{{ proj.subtitle }}</p>
    </a>
  </article>
{% endfor %}
