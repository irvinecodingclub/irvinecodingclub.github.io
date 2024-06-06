---
layout: page
title: Courses
comments: false
---

<!-- Featured
================================================== -->
<section class="featured-posts">

    <div class="row listfeaturedtag">

    {% for post in site.posts %}

        {% if post.path contains 'course' and post.path contains '2024' %}

            {% include featuredbox.html %}

        {% endif %}

    {% endfor %}

    </div>

</section>
