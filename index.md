---
layout: single          # plain page; sidebar stays intact
title: ""               # empty keeps the big H1 off
permalink: /            # make sure this is the root URL
classes: "home"         # optional, lets you style the page later
author_profile: true
# author_profile: true  # uncomment to repeat the avatar + links at top
---

## Biography

Write a couple of paragraphs about yourself here.  
You can use **Markdown** formatting, add images, lists, links—whatever
you like. Example:

> I am a PhD candidate at KAUST working on optimization, federated
> learning and structural variant analysis. My research focuses on …

## Recent News
{% assign items = site.news | sort: "date" | reverse %}
<ul class="news-list">
{% for n in items limit:3 %}
  <li>
    <strong><a href="{{ n.url | relative_url }}">{{ n.title }}</a></strong>
    <small>— {{ n.date | date: "%b %d, %Y" }}</small><br/>
    {{ n.summary | markdownify }}
  </li>
{% endfor %}
</ul>

---

## Papers
{% assign pubs = site.papers | sort: "year" | reverse %}
{% if pubs %}
<ul class="paper-list">
{% for p in pubs %}
  <li>{{ p.citation | markdownify }}</li>
{% endfor %}
</ul>
[→ full list](/papers/)
{% else %}
<p>No papers yet.</p>
{% endif %}