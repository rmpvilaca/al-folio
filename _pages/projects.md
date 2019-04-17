---
title: "projects"
layout: default
sitemap: false
permalink: /projects/
---

# Ongoing projects
{% for project in site.projects %}
<div class="project">
    <div class="thumbnail">
        {% if project.redirect %}
        <a href="{{ project.redirect | prepend: site.baseurl | prepend: site.url }}">
         {% else %}
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% endif %}  
        {% if project.img %}
       <img class="thumbnail" src="{{ site.url }}{{ site.baseurl }}/assets/img/{{project.img }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h1>{{ project.title }}</h1>
            <br/>
            <p>{{ project.type }}</p>
        </span>
        <p>{{ project.description }}</p>
        </a>
    </div>
</div>
{% endfor %}

<span>
    <br/> <br/> <br/> <br/> <br/> <br/> <br/> <br/> <br/>
</span>

# Past projects
{% for project in site.past_projects %}
<div class="project ">
    <div class="thumbnail">
        {% if project.redirect %}
        <a href="{{ project.redirect | prepend: site.baseurl | prepend: site.url }}">
         {% else %}
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% endif %}  
        {% if project.img %}
       <img class="thumbnail" src="{{ site.url }}{{ site.baseurl }}/assets/img/{{project.img }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h1>{{ project.title }}</h1>
            <br/>
            <p>{{ project.type }}</p>
        </span>
        <p>{{ project.description }}</p>
        </a>
    </div>
</div>
{% endfor %}