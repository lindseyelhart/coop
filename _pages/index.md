---
title: " "
layout: splash
classes: wide
author_profile: true
permalink: /
header:
  overlay_color: "#123054"
  overlay_image: /assets/images/skyline_img.jpeg
  actions:
    - label: "Read Latest"
      url: /posts/
excerpt: "A blog for the Bioinformatics & Data Science Cooperative at Fred Hutch"
feature_row:
  - title: "Posts"
    excerpt: "See posts from the Coop."
    url: /categories/
    btn_class: "btn--primary"
    btn_label: "Read more"
  - title: "Calendar"
    excerpt: "Find select upcoming Coop events."
    url: /calendar/
    btn_class: "btn--primary"
    btn_label: "See Events"
  - title: "About"
    excerpt: "More about the Fred Hutch Coop."
    url: /about/
    btn_class: "btn--primary"
    btn_label: "About Us"
share: true
---
{% for post in site.posts limit:1 %}
  <h1>
    <a href="{{ site.baseurl }}{{ post.url}}">{{ post.title }}</a>
  </h1>
  <p><i class="far fa-clock" aria-hidden="true"></i> {% include read-time.html %}</p>
  {% for contributor in site.contributors %}
  {% if post.author == contributor.title %}
  Written by: <a href="{{ site.baseurl }}{{ contributor.url }}"> {{ contributor.title }} - {{ contributor.position }}</a>
  {% break %}
  {% endif %}
  {% endfor %}
  
  {{ post.content }}

{% endfor %}

{% include feature_row %}