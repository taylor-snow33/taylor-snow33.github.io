---
layout: page
title: "Contributors"
icon: fas fa-users # Optional: FontAwesome icon
order: 4
permalink: /authors/
---
<ul>
  {% for author in site.data.authors %}
    {% assign author_data = author[1] %}
    <li>
      <a href="/authors/{{ author_data.id }}/">{{ author_data.name }}</a>
    </li>
  {% endfor %}
</ul>

