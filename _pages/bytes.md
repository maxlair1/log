---
layout: page
title: Bytes
---

<section class="bytes">
    <br/>
    <ul>
        {% assign sorted = site.bytes | sort: "date" | reverse %}
        {% for byte in sorted %}
            <li class="byte">
                <span class="meta">
                    <a href="https://maxlair.com">
                        <img class="pfp" src="/max_pfp.png" alt="icon" aria-label="Max Lair's profile picture" width="16" height="16"/>
                        <em>Max Lair</em>
                    </a> 
                    said
                    <time datetime="{{ byte.date | date_to_xmlschema }}">{{ byte.date | timeago }}</time>{% if byte.topic %}│<span class="flagger">on:</span>
                    <em>{{ byte.topic }}</em>
                    {% endif %}
                    <br/>
                </span>
                <p>
                    {{ byte.content | markdownify }}                    
                </p>
            </li>
        {% endfor %}
    </ul>
</section>
