---
page_id: profiles
layout: page
permalink: /people/
title: 成员
description: 实验室包括教授1人、副教授2人、博后2人、博士5人以及硕士7人，并与国内外知名学者长期合作。
categories: [教师, 博后, 博士, 硕士, 国内外合作伙伴]
nav: true
nav_order: 2

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - category: 教师
    image: zhun.png
    position: 教授
    research: 国家级青年人才
    name: 钟准
    website: https://zhunzhong.site
  - category: 教师
    image: lechao.png
    position: 副教授
    research: 黄山学者学术骨干
    name: 程乐超
    website: https://liygcheng.github.io/home/
  - category: 教师
    image: yaxiong.jpg
    position: 副教授
    research: 黄山学者学术骨干
    name: 王亚雄
    website: https://scholar.google.com/citations?user=lDChiR4AAAAJ&hl=zh-CN
  - category: 博后
    image: nan.png
    name: 普楠
    research: 特伦托大学 (长期合作)
  - category: 博后
    image: pic_girl.png
    name: 李文静
    research: 诺丁汉大学 （长期合作）
  - category: 博士
    image: dong.jpg
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
    image: pic_boy.png
    name: 沈磊
    position: 联合培养
    research: Federated Learning
    join_date: 2022
  - category: 博士
    image: yan.png
    name: 张研
    position: 硕博连读
    research: Video Recognition
    join_date: 2023级
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
  - category: 硕士
    image: zhenxing.png
    name: 张振兴
    position: 保研
    research: --
    join_date: 2023
  - category: 硕士
    image: wangjing.png
    name: 王兢
    position: 保研
    research: --
    join_date: 2024
  - category: 硕士
    image: yizai.png
    name: 杨奕在
    position: 保研
    research: --
    join_date: 2024
  - category: 硕士
    image: lihaiyang.png
    name: 李海洋
    position: 保研
    research: --
    join_date: 2024
  - category: 国内外合作伙伴
    image: nicu.png
    name: Nicu Sebe
    website: https://disi.unitn.it/~sebe/
    position: 特伦托大学
  - category: 国内外合作伙伴
    image: elisa.png
    name: Elisa Ricci
    position: 特伦托大学
    website: https://eliricci.eu/
  - category: 国内外合作伙伴
    image: liangzheng.png
    name: 郑良
    position: 澳大利亚国立大学
    website: https://zheng-lab.cecs.anu.edu.au/
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
    width: 210px;
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
