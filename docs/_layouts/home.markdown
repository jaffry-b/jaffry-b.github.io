---
layout: default
---

<div class="home">

    <h1 id="hdr" class="page-heading" style="text-align: center"></h1>

    <script type="text/javascript">
        var d = new Date();
        var weekday = new Array(7);
        weekday[0] = "Sunday";
        weekday[1] = "Monday";
        weekday[2] = "Tuesday";
        weekday[3] = "Wednesday";
        weekday[4] = "Thursday";
        weekday[5] = "Friday";
        weekday[6] = "Saturday";

        var n = weekday[d.getDay()];

        document.getElementById("hdr").innerHTML = `See you Space Cowboy...`
    </script>

    {{ content }}

    {%- if site.posts.size > 0 -%}
    <h2 class="post-list-heading">{{ page.list_title | default: "Posts" }}</h2>
    <ul class="post-list">
        {%- for post in site.posts -%}
        <li>
        {%- assign date_format = "%a, %b %-d, %Y @ %R" -%}
        <span class="post-meta">{{ post.date | date: date_format }} {{post.time}}</span>
        <h3>
            <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
            </a>
        </h3>
        {%- if site.show_excerpts -%}
            {{ post.excerpt }}
        {%- endif -%}
        </li>
        {%- endfor -%}
    </ul>

    {%- endif -%}

</div>