---
layout: default
title: Home
nav_order: 1
description: "CityU STC TA Center"
permalink: /
---

# CityU STC TA Center
{: .fs-9 }

### Get Started

Welcome to CityU STC TA Center. We're here for sharing technical knowledge and solving your problems quickly. In addition, we want you learn something from here as well. 

Pages on this site runs on Github.io nad is open to anyone not only CityU TAS. If you want to contribute or find something wrong, Please read more about becoming a contributor in [our GitHub repo](https://github.com/cityuseattle/cityuseattle.github.io#contributing).

#### Thank you for your time!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>