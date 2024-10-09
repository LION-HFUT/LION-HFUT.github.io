---
page_id: profiles
layout: page
permalink: /people/
title: People
description: Our LION includes 1 Professor, 2 Associate Professor, 2 Postdocs, 5 PhD students and 9 Master students. We also closely collaborate with international senior researchers.
categories: [Faculty, Postdoc, PhD, Master, Research Collaborator]
nav: true
nav_order: 2

profiles:
  # if you want to include more than one profile, just replicate the following block
  # and create one content file for each profile inside _pages/
  - category: Faculty
    image: zhun.png
    position: Professor
    # research: 国家级青年人才
    name: Zhun Zhong
    website: https://zhunzhong.site
  - category: Faculty
    image: lechao.png
    position: Associate Professor
    #research: 黄山学者学术骨干
    name: Lechao Cheng
    website: https://liygcheng.github.io/home/
  - category: Faculty
    image: yaxiong.jpg
    position: Associate Professor
    #research: 黄山学者学术骨干
    name: Yaxiong Wang
    website: https://scholar.google.com/citations?user=lDChiR4AAAAJ&hl=zh-CN
  - category: Postdoc
    image: nan.png
    name: Nan Pu
    research: University of Trento (Co-Supervised)
  - category: Faculty
    image: wenjing.png
    name: Wenjing Li
    position: Lecturer
    # research: University of Trento (Co-Supervised)
  - category: PhD
    image: dong.jpg
    name: Dong Zhao
    position: University of Trento (Co-Supervised)
    research: Segmentation
    join_date: 2020 Fall
  - category: PhD
    image: fengxiang.png
    name: Fengxiang Yang
    position: Xiamen University (Co-Supervised)
    research: Retrieval
    join_date: 2020 Fall
  - category: PhD
    image: mingxuan.png
    name: Mingxuan Liu
    position: University of Trento (Co-Supervised)
    research: Open-Set
    join_date: 2022 Fall
  - category: PhD
    image: pic_boy.png
    name: Lei Shen
    position: Hong Kong Baptist University (Co-Supervised)
    research: Federated Learning
    join_date: 2022 Fall
  - category: PhD
    image: yan.png
    name: Yan Zhang
    position: Co-Supervised
    research: Video Recognition
    join_date: 2023 Fall
  - category: Master
    image: chentaocao.jpg
    name: Chentao Cao
    position: Hong Kong Baptist University (Co-Supervised)
    research: OOD Detection
    join_date: 2021 Fall
  - category: Master
    image: haiyang.png
    name: Haiyang Zheng
    position: Harbin Institute of Technology (Co-Supervised)
    research: Novel Class Discovery
    join_date: 2021 FALL
  - category: Master
    image: weiwang.png
    name: Wei Wang
    position: Western University (Co-Supervised)
    research: Domain Adaptation
    join_date: 2021
  - category: Master
    image: zhenxing.png
    name: Zhenxing Zhang
    position: Co-Supervised
    research: --
    join_date: 2023
  - category: Master
    image: wangjing.png
    name: Jing Wang
    # position: 保研
    research: --
    join_date: 2024 Fall
  - category: Master
    image: yizai.png
    name: Yizai Yang
    # position: 保研
    research: --
    join_date: 2024 Fall
  - category: Master
    image: lihaiyang.png
    name: Haiyang Li
    # position: 保研
    research: --
    join_date: 2024 Fall
  - category: Master
    image: qihang.png
    name: Qihang Wang
    # position: 保研
    research: --
    join_date: 2024 Fall
  - category: Master
    image: pic_boy.png
    name: Yubin Wang
    # position: 保研
    research: --
    join_date: 2024 Fall
  - category: Master
    image: sirui.png
    name: Sirui He
    # position: 保研
    research: --
    join_date: 2025 Fall
  - category: Master
    image: pic_boy.png
    name: Hao Xu
    # position: 保研
    research: --
    join_date: 2025 Fall
  - category: Master
    image: pic_boy.png
    name: Jinyuan Qin
    # position: 保研
    research: --
    join_date: 2025 Fall
  - category: Master
    image: gaoyu.png
    name: Yu Gao
    # position: 保研
    research: --
    join_date: 2025 Fall
  - category: Master
    image: lele.png
    name: Lele Hu
    # position: 保研
    research: --
    join_date: 2025 Fall
  - category: Master
    image: zhaoxiang.png
    name: Zhaoxiang Bi
    # position: 保研
    research: --
    join_date: 2025 Fall
  - category: Research Collaborator
    image: nicu.png
    name: Nicu Sebe
    position: University of Trento
    website: https://disi.unitn.it/~sebe/
  - category: Research Collaborator
    image: elisa.png
    name: Elisa Ricci
    position: University of Trento
    website: https://eliricci.eu/
  - category: Research Collaborator
    image: liangzheng.png
    name: Liang Zheng
    position: Australian National University
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
    width: 220px;
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