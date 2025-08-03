---
title: Talks
layout: single        # ← change from “collection” to “page”
classes: wide       # optional: wider text block
permalink: /talks/
---

{% assign talks = site.talks | sort:"date" | reverse %}
{% if talks %}
<ol class="talk-list">
{% for t in talks %}
<li>
  <p><strong>{{ t.title }}</strong></p>
  <p>{{ t.date | date: "%b %d, %Y" }} — {{ t.venue }}, {{ t.place }}</p>
  {% if t.slides %}
    <p><a href="{{ t.slides | relative_url }}">Slides</a></p>
  {% endif %}
</li>
{% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
</ol>
{% else %}
<p>No talks yet.</p>
{% endif %}

