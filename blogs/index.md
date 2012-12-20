---
layout: default
title: All Pages 
header: Pages
group: navigation
---

## Member blogs ##
<ul>
	{% assign pages_list = site.pages %}  
	{% assign group = 'member_blogs' %}
  	{% include pages_list %}
</ul>