---
layout: default
title: 'Member listing' 
header: Members
---
<div class="twelve columns">
  <h3>Incomplete member list.</h3>(In order of page generation)<p/>
  {% assign pages_list = site.pages %}
   {% assign group = 'members' %}
    {% for node in pages_list %}
     {% if node.title != null %}
      {% if group == null or group == node.group %}
         <div class="panel">
          {% if page.url == node.url %}
           <h5><a href="{{ BASE_PATH }}{{node.url}}" class="active">{{node.title}}</a></h5>
           {% else %}
           <h5><a href="{{ BASE_PATH }}{{node.url}}">{{node.title}}</a></h5>
          {% endif %}
         </div>
        {% endif %}
      {% endif %}
    {% endfor %}
</div>