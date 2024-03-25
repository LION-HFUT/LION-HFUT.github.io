---
page_id: profiles
layout: page
permalink: /people/
title: 成员
description: 实验室成员
categories: [博士, 硕士]
nav: true
nav_order: 2

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - category: 博士
    image: prof_pic.jpg
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: prof_pic.jpg
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: prof_pic.jpg
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: prof_pic.jpg
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: prof_pic.jpg
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: prof_pic.jpg
    position: PHD
    research: CV
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    position: Master
    research: ML
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    position: Master
    research: ML
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    position: Master
    research: ML
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    position: Master
    research: ML
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    position: Master
    research: ML
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    position: Master
    research: ML
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    position: Master
    research: ML
    join_date: 2024
---

<style>
  .category-section {
    margin-bottom: 40px;
  }
  .profile-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 20px;
  }
  .profile {
    text-align: center;
  }
  .profile img {
    max-width: 100%;
    height: auto;
    border-radius: 50%;
  }
  .profile-info {
    margin-top: 8px;
  }
</style>


<div class="post">
  <article>
    {% if page.profiles %}
      {% for category in page.categories %}
        <div class="category-section">
          <h2>{{ category }}</h2>
          <div class="profile-grid">
            {% for profile in page.profiles %}
              {% if profile.category == category %}
                <div class="profile">
                  {% if profile.image %}
                    profile.image
                    <img src="assets/img/{{ profile.image }}" alt="{{ profile.name }}">
                  {% endif %}
                  <div class="profile-info">
                    <div>{{ profile.position }}</div>
                    <div>{{ profile.research }}</div>
                    <div>{{ profile.join_date }}</div>
                  </div>
                </div>
              {% endif %}
            {% endfor %}
          </div>
        </div>
      {% endfor %}
    {% endif %}
  </article>
</div>
