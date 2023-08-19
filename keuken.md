---
layout: post
title: Keuken
permalink: /keuken/
content-type: eg
---

<style>
.category-content a {
    text-decoration: none;
    color: #4183c4;
}

.category-content a:hover {
    text-decoration: underline;
    color: #4183c4;
}
</style>

<main>
    <div class="tag-overview-wrapper">
    {% assign keuken =  site.notes | map: 'keuken' | join: ' '  | split: ' ' | uniq %}
    {% for tag in keuken %}
        <div class="tag-overview" id="{{ tag }}">
        <h3 id="{{ tag }}">{{ tag | capitalize }}</h3>
        {%- for note in site.notes -%}
            {%- if note.keuken contains tag -%}
                <li style="padding-bottom: 0.6em; list-style: none;"><a href="{{note.url}}">{{ note.title }}</a></li>
            {%- endif -%}
        {%- endfor -%}
        </div>
    {%- endfor -%}
    </div>
    <br/>
    <br/>
</main>