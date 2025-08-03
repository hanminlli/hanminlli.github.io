---
layout: single          # plain page; sidebar stays intact
title: ""               # empty keeps the big H1 off
permalink: /            # make sure this is the root URL
classes: "home"         # optional, lets you style the page later
author_profile: true
# author_profile: true  # uncomment to repeat the avatar + links at top
---

## Biography

Hi there! I am **Hanmin Li**, a PhD candidate in Computer Science at [KAUST](https://www.kaust.edu.sa/en/) under the supervision of [Prof. Peter Richtárik](https://richtarik.org). My research focus lies at the intersection of optimization and large language models (LLMs), with a focus on training efficiency and scalability. I am also interested in distributed training and the theoretical foundations of learning from decentralized data. More broadly, my interests also extends to the theory of modern machine learning, including first-order methods, convex and non-convex optimization, and operator theory, as well as applied areas like deep learning and language modeling.
{: .text-justify}


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