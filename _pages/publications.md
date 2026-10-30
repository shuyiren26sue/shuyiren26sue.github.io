---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
<div class="wordwrap">
  You can also find my articles on
  <a href="{{ site.author.googlescholar }}">Google Scholar</a>.
</div>
{% endif %}

<p>Publications detected: {{ site.publications | size }}</p>

{% if site.publication_category %}

  {% for category in site.publication_category %}
    {% assign title_shown = false %}

    {% for post in site.publications reversed %}
      {% if post.category == category[0] %}

        {% unless title_shown %}
## {{ category[1].title }}
          {% assign title_shown = true %}
        {% endunless %}

        {% include archive-single.html %}

      {% endif %}
    {% endfor %}
  {% endfor %}

{% else %}

  {% for post in site.publications reversed %}
    {% include archive-single.html %}
  {% endfor %}

{% endif %}
