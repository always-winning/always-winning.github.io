---
layout: page
title: Nieuws
permalink: /nieuws/
---

{%- if site.posts.size > 0 -%}
<ul class="post-list">
    {%- for post in site.posts -%}
    <li>
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    {%- if post.coverimage -%}
        <img src="{{ post.coverimage }}" />
    {%- else -%}
        <img src="/assets/images/article.svg" alt="Default cover image" />
    {%- endif -%}
    <span class="post-meta">{{ post.date | date: date_format }}</span>

    <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
        {{ post.title | escape }}
        </a>
    </h3>
    {%- for category in post.categories -%}
        <span class="category_tag {{ category | downcase | replace: ' ', '-' }}">{{ category | capitalize }}</span>
    {%- endfor -%}
    {%- if site.show_excerpts -%}
        {{ post.excerpt }}
    {%- endif -%}
    </li>
    {%- endfor -%}
</ul>

<p class="rss-subscribe">Abonneer <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>
{%- endif -%}

{%- if site.posts.size > 0 -%}
<div class="recent-posts">
    <h2>Recente artikelen</h2>
    <ul class="recent-post-list">
        {%- assign recent_posts = site.posts | where: "id", "!=" page.id | sort: "date" | reverse | limit: 5 -%}
        {%- for post in recent_posts -%}
        <li>
            <span class="post-meta">{{ post.date | date: date_format }}</span>
            <h3>
                <a class="post-link" href="{{ post.url | relative_url }}">
                    {{ post.title | escape }}
                </a>
            </h3>
        </li>
        {%- endfor -%}
    </ul>
</div>
{%- endif -%}
