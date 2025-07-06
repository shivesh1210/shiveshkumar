---
layout: page
permalink: /teaching/
title: teaching
description: Courses taught over the years.
nav: true
nav_order: 7
---

<div class="container mt-4">
  {% for item in site.data.teaching %}
    <div class="card my-3 p-3" style="border: 1px solid #ec407a;">
      <div class="row">
        <div class="col-md-3 text-center">
          <span class="badge danger-color text-uppercase">{{ item.start }} – {{ item.end }}</span><br>
          <small>{{ item.location }}</small>
        </div>
        <div class="col-md-9">
          <h5>{{ item.course }}</h5>
          <p class="mb-1"><strong>{{ item.university }}</strong> – {{ item.level }}</p>
          <p class="text-muted">Credits: {{ item.credits }}</p>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
