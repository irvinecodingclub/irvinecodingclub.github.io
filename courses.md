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

        {% if post.course == true and post.year == 2022 %}

            {% include featuredbox.html %}

        {% endif %}

    {% endfor %}

    </div>

</section>
