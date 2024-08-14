---
layout: default
title: OSIUM Newsletter
description: Check our news and subscribe
---

---

# Follow Us on X

<a class="twitter-timeline" href="https://twitter.com/OpenScienceUM?ref_src=twsrc%5Etfw" data-tweet-limit="1" data-height="300">Tweets by OpenScienceUM</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

---

# Subscribe to Our Newsletter

<a href="https://www.lists.uni-marburg.de/lists/sympa/subscribe/open-science?previous_action=info">Subscribe to our newsletter</a>

Anyone from the Philipps-University Marburg and beyond can attend and participate in our events. To get notified of our activities, you can subscribe to our mailing list.


# Newsletter Archive

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%d %B %Y" }}
  </li>
{% endfor %}
</ul>

## another format

{% for post in site.posts %}
* {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}

## Tags

{% assign rawtags = "" %}
{% for post in site.posts %}
{% assign ttags = post.tags | join:'|' | append:'|' %}
{% assign rawtags = rawtags | append:ttags %}
{% endfor %}

{% assign rawtags = rawtags | split:'|' | sort %}

{% assign tags = "" %}

{% for tag in rawtags %}
{% if tag != "" %}

{% if tags == "" %}
{% assign tags = tag | split:'|' %}
{% endif %}

{% unless tags contains tag %}
{% assign tags = tags | join:'|' | append:'|' | append:tag | split:'|' %}
{% endunless %}
{% endif %}
{% endfor %}


<p>
{% for tag in tags %}
<a href="#{{ tag | slugify }}" class="codinfox-tag-mark"> {{ tag }} </a> &nbsp;&nbsp;
{% endfor %}
</p>

{% for tag in tags %}
<h5 id="{{ tag | slugify }}">{{ tag }}</h5>
<ul class="codinfox-category-list">
{% for post in site.posts %}
{% if post.tags contains tag %}
<li>
<p>
<a href="{{ post.url }}">
{{ post.title }}
<small>{{ post.date | date_to_string }}</small>
</a>
{% for tag in post.tags %}
<a class="codinfox-tag-mark" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
{% endfor %}
</p>
</li>
{% endif %}
{% endfor %}
</ul>
{% endfor %}


---


[back](./)
