---
layout: plain
title: "Reduction Zoo"
date: 2017-02-22
---

{% assign problems = site.data.problems %}

<h2>List of problems</h2>

{% include _search_problems.html %}

{% for tuple in problems %}
{% assign prob = tuple[1] %}
<div class="problem">
<h3 class="problem-name" data-name="{{ prob.name }}">{{ prob.name }}</h3>
<div class="row problem-input">
<div class="subt col-sm-4 col-md-3 col-lg-2">Input:</div>
<div class="desc col-sm-8 col-md-9 col-lg-10">{{ prob.input }}</div>
</div>
<div class="row problem-question">
<div class="subt col-sm-4 col-md-3 col-lg-2">Question:</div>
<div class="desc col-sm-8 col-md-9 col-lg-10">{{ prob.question }}</div>
</div>
</div>
{% endfor %}

