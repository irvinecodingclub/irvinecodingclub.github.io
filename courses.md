---
layout: page
title: 2024 Course Catalog
comments: false
---

<!-- Featured
================================================== -->
<section class="featured-posts">
    
    <div class="row listfeaturedtag">

        <div>
            <h4>Enroll in ICC Courses <a href="{{ site.baseurl }}/enroll">here</a>!</h4>
        </div>
        {% for course in site.courses %}

            {% if course.path contains '2024' %}
                
                <!-- begin course -->
                <div class="col-sm-6">
                <div class="card">
                    <div class="row">
                        <div class="col-md-5 wrapthumbnail">
                            <a href="{{ course.url | absolute_url }}">
                            <div class="thumbnail" style="background-image:url({{ site.baseurl }}/{{ course.image2 }});">
                            </div>
                            </a>
                        </div>
                        <div class="col-md-7">
                            <div class="card-block">
                                <h2 class="card-title"><a href="{{ course.url | absolute_url }}">{{ course.name }}</a></h2>
                                <h4 class="card-text">{{ course.desc | strip_html | truncatewords:25 }}</h4>
                                <div class="metafooter">
                                    <div class="wrapfooter">
                                        <span class="post-level">Course Level: {{ course.level }}</span>
                                        <span class="post-date"> | Starts {{ course.start_date }}</span>
                                        <span class="post-read-more"><a href="{{ course.url | absolute_url }}" title="Read Story"><i class="fa fa-link"></i></a></span>
                                        <div class="clearfix"></div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                </div>
                <!-- end course -->

            {% endif %}

        {% endfor %}

    </div>

</section>
