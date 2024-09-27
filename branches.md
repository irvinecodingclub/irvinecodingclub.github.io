---
layout: page
title: Branches
comments: false
---

<!-- Featured
================================================== -->
<section class="featured-posts">
    
    <div class="row listfeaturedtag">

        <div>
            <h4>Learn about our branches across various school campuses!</h4>
        </div>
        <br><br><br>
        <!-- {% for branch in site.branches %}
                
            <!-- begin branch -->
            <div class="card">
                <div class="row">
                    <div class="col-md-5 wrapthumbnail">
                        <a href="{{ branch.url | absolute_url }}">
                        <div class="thumbnail" style="background-image:url({{ site.baseurl }}/{{ branch.image }});">
                        </div>
                        </a>
                    </div>
                    <br><br><br>
                    <h2 class="card-title offset-1"><br><a href="{{ branch.url | absolute_url }}">{{ branch.name }}</a></h2>
                </div>
            </div>
            <!-- end branch -->

        {% endfor %}

    </div>

</section>
