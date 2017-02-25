---
layout: plain
title: "Reduction Zoo"
date: 2017-02-22
---


{% assign problems = site.problems %}

<h2 style="padding-top:60px">List of problems</h2>

{% include _search_problems.html %}

{% for prob in problems %}
<div class="problem">
<h3 style="padding-top:15px" class="problem-name pname" data-name="{{ prob.name }}"><a href="{{ prob.url }}">{{ prob.name }}</a></h3>
<div class="row problem-input">
<div class="subt col-sm-4 col-md-3 col-lg-2">Input:</div>
<div class="desc col-sm-8 col-md-9 col-lg-10">{{ prob.input }}</div>
</div>
<div class="row problem-question">
<div class="subt col-sm-4 col-md-3 col-lg-2">Question:</div>
<div class="desc col-sm-8 col-md-9 col-lg-10">{{ prob.question }}</div>
</div>
<div class="row problem-reductions">
<div class="subt col-sm-4 col-md-3 col-lg-2">Reductions:</div>
<div class="desc col-sm-8 col-md-9 col-lg-10">
{% assign reductions = site.reductions | where: "from", prob.name %}
{% for reduction in reductions %}
 <a class="pname" href="{{ reduction.url }}">{{reduction.from}} $\leq$ {{reduction.to}}</a>
{% endfor %}
{% assign reductions = site.reductions | where: "to", prob.name %}
{% for reduction in reductions %}
 <a class="pname" href="{{ reduction.url }}">{{reduction.from}} $\leq$ {{reduction.to}}</a>
{% endfor %}
</div>
</div>
</div>
{% endfor %}
