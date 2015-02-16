---
layout: default
title: Blob
permalink: /blog/
---
<h1>Blob</h1>

<div class="posts">
  {% for post in site.posts %}
    
    <article class="post">    
      
      <h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>

      <div class="entry">
        {{ post.content | truncatewords:10}}
      </div>
    </article>
  {% endfor %}
</div>