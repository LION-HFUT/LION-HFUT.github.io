---
page_id: profiles
layout: page
permalink: /people/
title: 成员
description: 实验室成员
categories: [教师, 博后, 博士, 硕士]
nav: true
nav_order: 2

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - category: 教师
    image: prof_pic.jpg
    position: 教授
    name: 李小龙
  - category: 教师
    image: 1.jpg
    position: 教授
    name: 李小龙2
  - category: 教师
    image: 2.jpg
    position: 教授
    name: 李小龙3
  - category: 教师
    image: 3.jpg
    position: 教授
    name: 李小龙4
  - category: 教师
    image: 4.jpg
    position: 教授
    name: 李小龙5
  - category: 教师
    image: 5.jpg
    position: 教授
    name: 李小龙6
  - category: 博后
    image: 6.jpg
    name: 关羽1
    position: Postdoc
    research: CV
    join_date: 2024
  - category: 博士
    image: 7.jpg
    name: 赵子龙1
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: 8.jpg
    name: 赵子龙2
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: 9.jpg
    name: 赵子龙3
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: 10.jpg
    name: 赵子龙4
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: 11.jpg
    name: 赵子龙5
    position: PHD
    research: CV
    join_date: 2024
  - category: 博士
    image: 12.jpg
    name: 赵子龙6
    position: PHD
    research: CV
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    name: 张飞1
    position: Master
    research: CV
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    name: 张飞2
    position: Master
    research: CV
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    name: 张飞3
    position: Master
    research: CV
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    name: 张飞4
    position: Master
    research: CV
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    name: 张飞5
    position: Master
    research: CV
    join_date: 2024
  - category: 硕士
    image: prof_pic.jpg
    name: 张飞6
    position: Master
    research: CV
    join_date: 2024
---

<style>
  .category-section {
    margin-bottom: 60px;
  }
  .profile-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 10px;
  }
  .profile {
    text-align: center;
    width: 190px;
  }
  .profile img {
    max-width: 100%;
    height: auto;
    border-radius: 10%;
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
          <hr />
          <div class="profile-grid">
            {% for profile in page.profiles %}
              {% if profile.category == category %}
                <div class="profile">
                  {% if profile.image %}
                    <img src="/assets/img/{{ profile.image }}" alt="{{ profile.name }}">
                  {% endif %}
                  <div class="profile-info">
                    <div>{{ profile.name }}</div>
                    {% if profile.position %}
                        <div>{{ profile.position }}</div>
                    {% endif %}
                    {% if profile.research %}
                        <div>{{ profile.research }}</div>
                    {% endif %}
                    {% if profile.join_date %}
                        <div>{{ profile.join_date}}</div>
                    {% endif %}
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
