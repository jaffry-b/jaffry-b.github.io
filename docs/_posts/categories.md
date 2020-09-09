---
layout: page
permalink: /categories/
title: Categories
---


<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>

    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>

 
 {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%} {{ page.date | date: date_format }} {%- if page.author -%} • {{ page.author }} {%- endif -%}

&nbsp;
&nbsp;

{% for category in page.categories %}
<a href="{{site.baseurl}}/categories/#{{category|slugize}}">{{category}}</a>
{% unless forloop.last %},{% endunless %}
{% endfor %} </p>

{{ content }}

{%- if site.disqus.shortname -%} {%- include disqus_comments.html -%} {%- endif -%}