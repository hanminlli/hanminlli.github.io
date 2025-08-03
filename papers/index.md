---
title: Papers
layout: page        # ← change from “collection” to “page”
classes: wide       # optional: wider text block
permalink: /papers/
---

{% assign pubs = site.papers | sort:"year" | reverse %}
{% if pubs %}
<ol class="paper-list">
{% for p in pubs %}
<li>

<p><strong>{{ p.title }}</strong></p>

{%- assign authors = p.authors
     | replace: "Hanmin Li",
                "<strong><u>Hanmin&nbsp;Li</u></strong>" -%}

<p>
  <span class="authors">{{ authors | raw }}</span>,
  <em>{{ p.venue }}</em>.
  {% if p.arxiv %} · <a href="{{ p.arxiv }}">paper</a>{% endif %}
  {% if p.cite  %} · <a href="{{ p.cite }}">BibTeX</a>{% endif %}
</p>

<p>{{ p.summary | markdownify }}</p>

</li>

{% unless forloop.last %}
<hr>
{% endunless %}

{% endfor %}
</ol>
{% endif %}

