---
layout: single          # plain page; sidebar stays intact
title: ""               # empty keeps the big H1 off
permalink: /            # make sure this is the root URL
classes: "home"         # optional, lets you style the page later
author_profile: true
# author_profile: true  # uncomment to repeat the avatar + links at top
classes: wide  
---

## Biography

Hi there! I am **Hanmin Li**, a PhD candidate in Computer Science at [KAUST](https://www.kaust.edu.sa/en/) under the supervision of [Prof. Peter Richtárik](https://richtarik.org). My research focus lies at the intersection of optimization and large language models (LLMs), with a focus on training efficiency and scalability. I am also interested in distributed training and the theoretical foundations of learning from decentralized data. 
{: .text-justify}

More broadly, my interests also extends to the theory of modern machine learning, including first-order methods, convex and non-convex optimization, and operator theory, as well as applied areas like deep learning and language modeling.
{: .text-justify}

Before starting my Ph.D., I earned my master degress in **Computer Science** also at KAUST, after completing a **B.S. in Computer Science and Technology** at the [School of the Gifted Young](https://en.scgy.ustc.edu.cn/main.htm) in the [University of Science and Technology of China (USTC)](https://en.ustc.edu.cn/).
{: .text-justify}

Currently, I am working on: 
- Distributed training of large language models (LLMs), including experience with [large-scale GPU clusters](https://docs.hpc.kaust.edu.sa/systems/shaheen3/index.html) and training using PyTorch Distributed Data Parallel (DDP).
- Efficient optimizer design for large-scale training, with a focus on advancing the [Muon](https://kellerjordan.github.io/posts/muon/) optimizer to achieve faster convergence and improved scalability.
- Designing efficient algorithms for large language models (LLMs), with a focus on both theoretical analysis and empirical validation.

For any inquiries, feel free to contact me at <a href="mailto:hanmin.li@kaust.edu.sa">hanmin.li@kaust.edu.sa</a>.

> I am currently **open** to internship opportunities in related areas.


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
{% assign pubs = site.papers | sort:"year" | reverse %}
{% if pubs %}
<ul class="paper-list">
{% for p in pubs %}
<li>
  <strong>{{ p.title }}</strong><br>

  {%- capture highlighted_authors -%}
    {{ p.authors
       | replace: "Hanmin Li",
                  "<strong><u>Hanmin&nbsp;Li</u></strong>" }}
  {%- endcapture -%}

  <span class="authors">{{ highlighted_authors | raw }}</span>,
  <em>{{ p.venue }}</em>.
  • {% if p.arxiv %}<a href="{{ p.arxiv }}">[paper]</a>{% endif %}
  {% if p.cite  %}{% if p.arxiv %} • {% endif %}
  <a href="{{ p.cite }}">[BibTex]</a>{% endif %}<br>
  <span class="summary">{{ p.summary | markdownify }}</span>
</li>
{% unless forloop.last %}
<hr class="paper-divider">   <!-- ★ new divider between papers ★ -->
{% endunless %}
{% endfor %}
</ul>

<p><a href="/papers/">→ full list</a></p>
{% else %}
<p>No papers yet.</p>
{% endif %}

---

## Reviewer Services
- [NeurIPS](https://neurips.cc/) 24', 25'
- [NeurIPS OPT-ML](https://opt-ml.org/) 24' 
- [ICLR](https://iclr.cc/) 25'
- [ICML](https://icml.cc/) 25'
- [JMLR](https://www.jmlr.org/)
- [IEEE TNNLS](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=5962385)
- [IEEE TSP](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=78)
-  Optimization Methods and Software.