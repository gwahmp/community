---
layout: default
---

<div class="container mt-5">
    <div class="row">

<!-- Sidebar -->
<aside class="col-md-4 col-lg-4">


</aside>
<!-- Main Content -->
<main class="col-md-8 col-lg-8">

<h1>Connect with community members</h1><hr/>



<!-- 
{% assign users = site.data %}
<div class="list-group">
{% for user in users %}
{% assign us = user | last %} 

<div class="list-group-item bg-light mb-3 py-3">
<a class="text-dark" href="../{{ user[0]}}">
<h3 class="card-title">{{ us.n }}</h3> 
<p class="card-text">{{ us.d }}</p> 
</a>
</div>
{% endfor %}
</div>
-->


{% assign user_pages = site.pages | where_exp: "page", "page.url contains '/user/'" %}
{% if user_pages.size > 0 %}
{% assign shuffled_users = user_pages | sort: 'random' | limit: -1 %}
<ul class="list-group list-group-flush">
{% for page in shuffled_users %}

<li class="list-group-item ps-0">
<a aria-label="{{ page.title }}" title="{{ page.title }}" href="{{ site.url }}{{ page.url | remove: '.md' | remove: '.html' }}">
{{ page.title }}
</a>
<a class="text-dark" href="../user/{{page.u}}">
<h3 class="card-title">{{ page.n }}</h3> 
<p class="card-text">{{ page.d }}</p> 
</a>
</li>
{% endfor %}
</ul>            
{% else %}
<div class="col">
<p>No projects found.</p>
</div>
{% endif %}



</main>

</div>
</div>
