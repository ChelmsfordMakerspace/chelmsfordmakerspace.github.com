---
layout: default
title: 'Member listing' 
header: Members
---

##Member listing
<ul>
	{% assign pages_list = site.pages %}  
	{% assign group = 'members' %}
  	{% include pages_list %}
</ul>