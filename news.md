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

<!-- {% for post in site.posts %}
* {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %} -->


---


[back](./)
