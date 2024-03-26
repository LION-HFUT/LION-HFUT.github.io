---
page_id: profiles
layout: page
permalink: /people/
title: 成员
description: 实验室包括教授5人、博后1人、博士5人以及硕士10人，并与国内外知名学者长期合作。
categories: [教师, 博后, 博士, 硕士, 国内外合作伙伴]
nav: true
nav_order: 2

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - category: 教师
    image: zhun.png
    position: 教授
    name: 钟准
    website: zhunzhong.site
  - category: 教师
    image: 1.jpg
    position: 教授
    name: 关羽
    website: zhunzhong.site
  - category: 博后
    image: nan.png
    name: 普楠
    research: Computer Vision
  - category: 博后
    image: pic_girl.png
    name: 李文静
    research: Computer Vision
  - category: 博士
    image: dong.png
    name: 赵栋
    position: 联合培养
    research: Segmentation
    join_date: 2020级
  - category: 博士
    image: fengxiang.png
    name: 杨丰祥
    position: 联合培养
    research: Retrieval
    join_date: 2020级
  - category: 博士
    image: mingxuan.png
    name: 刘明轩
    position: 联合培养
    research: Open-Set
    join_date: 2022
  - category: 博士
    image: yan.png
    name: 张研
    position: 硕博连读
    research: Video Recognition
    join_date: 2023级
  - category: 博士
    image: pic_boy.png
    name: 沈磊
    position: 联合培养
    research: Federated Learning
    join_date: 2022
  - category: 硕士
    image: chentaocao.jpg
    name: 曹晨涛
    position: 联合培养
    research: OOD Detection
    join_date: 2021
  - category: 硕士
    image: haiyang.png
    name: 郑海阳
    position: 联合培养
    research: Novel Class Discovery
    join_date: 2021
  - category: 硕士
    image: weiwang.png
    name: 汪炜
    position: 联合培养
    research: Domain Adaptation
    join_date: 2021
  - category: 国内外合作伙伴
    image: prof_pic.jpg
    name: Nicu Sebe
    position: 特伦托大学
  - category: 国内外合作伙伴
    image: prof_girl.jpg
    name: Elisa Ricci
    position: 特伦托大学
  - category: 国内外合作伙伴
    image: prof_pic.jpg
    name: 郑良
    position: 澳大利亚国立大学
  - category: 国内外合作伙伴
    image: prof_pic.jpg
    name: 罗志明
    position: 厦门大学
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
                    <img src="/assets/img/people/{{ profile.image }}" alt="{{ profile.name }}">
                  {% endif %}
                  <div class="profile-info">
                    {% if profile.website %}
                        <a href="{{profile.website}}" target="_blank"><b>{{profile.name}}</b></a>
                    {% else %}
                        <div>{{ profile.name }}</div>
                    {% endif %}
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
