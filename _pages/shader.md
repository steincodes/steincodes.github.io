---
layout: archive
title: "Shaders"
author_profile: true
permalink: /shader/
classes: wide
---
<hr/>
<section id="post" class="taxonomy__section">
<div class="entries-{{ page.entries_layout | default: 'list' }}">
    {%- for post in site.tags[page.title] -%}
    {% include archive-single.html %}
    {%- endfor -%}
</div>
<a href="#site-nav" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }} &uarr;</a>
</section>