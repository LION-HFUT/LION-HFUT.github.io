# CLAUDE.md — LION 实验室网站维护手册

## 项目概述

- **网站**：LION（Lab for Intelligence and visiON）实验室官网
- **地址**：https://lion-hfut.github.io
- **负责人**：钟准，zhunzhong007@gmail.com，Google Scholar: qc6CJjYAAAAJ
- **技术栈**：Jekyll + al-folio 多语言主题（jekyll-polyglot）
- **语言**：中文 `cn-cn`（主用）、英文 `en-us`，两者必须同步维护
- **部署**：push 到 `main` 分支后，GitHub Actions 自动构建并发布（约 3–5 分钟生效）

> `pt-br`（葡萄牙语）是上游主题留下的示例，**不需要维护**。

---

## 目录结构（关键文件）

```
LION-HFUT.github.io/
│
├── _config.yml                  # 全局配置：语言、Scholar、社交账号、功能开关
│
├── _bibliography/
│   └── papers.bib               # 所有论文（BibTeX），唯一数据源，按年倒序排列
│
├── _news/
│   ├── cn-cn/                   # 中文公告（announcement_YYYYMMDD.md）
│   └── en-us/                   # 英文公告（同名文件，内容对应）
│
├── _pages/
│   ├── cn-cn/
│   │   ├── about.md             # 主页（permalink: /，实验室简介）
│   │   ├── profiles.md          # 成员页（YAML frontmatter 驱动，无需改 body）
│   │   ├── publications.md      # 论文页（自动读 papers.bib，通常不改）
│   │   ├── joinus.md            # 加入我们（招生简章，layout: page1）
│   │   └── news.md              # 新闻页（自动聚合 _news/，通常不改）
│   └── en-us/                   # 英文版（结构相同，每次同步修改）
│
├── _data/
│   ├── coauthors.yml            # 作者姓名 → 个人主页 URL 映射（论文页自动加链接）
│   ├── venues.yml               # 会议/期刊名称 → 徽章颜色
│   ├── cn-cn/strings.yml        # 中文界面文本（页脚、新闻标题等）
│   └── en-us/strings.yml        # 英文界面文本
│
└── assets/
    └── img/
        ├── people/              # 成员头像（文件名对应 profiles.md 中的 image 字段）
        └── publication_preview/ # 论文缩略图（对应 papers.bib 中的 preview 字段）
```

---

## 高频维护任务

### 1. 发布新闻公告

在 `_news/cn-cn/` 和 `_news/en-us/` 各新建一个同名文件：

**文件名**：`announcement_YYYYMMDD.md`（8位日期，如 `announcement_20250526.md`）

```markdown
---
layout: post
date: 2025-05-26 10:00:00-0400
inline: true
related_posts: false
---

实验室两篇论文被 ICCV 2025 接收，其中一篇入选 Oral（Top 2%）。恭喜各位同学！
```

英文版：
```markdown
---
layout: post
date: 2025-05-26 10:00:00-0400
inline: true
related_posts: false
---

Two papers are accepted by ICCV 2025, one of which is selected as Oral (Top 2%). Congratulations to all!
```

- `inline: true`：公告显示在主页滚动栏中
- 日期决定显示顺序（倒序，新的在前）
- **必须同时创建中英文两个文件**

---

### 2. 添加/更新成员

编辑 `_pages/cn-cn/profiles.md`（**同步编辑** `_pages/en-us/profiles.md`）的 frontmatter：

```yaml
- category: 硕士              # 分类：教师 / 博后 / 博士 / 硕士 / 本科 / 毕业生 / 国内外合作伙伴
  image: filename.png         # 照片，放到 assets/img/people/（文件名全小写）
  name: 姓名
  position: 联合培养           # 可选：职位、备注
  research: Novel Class Discovery  # 可选：研究方向
  join_date: 2025             # 可选：入学年份，毕业生写区间如 2021-2024
  website: https://...        # 可选：个人主页
```

**成员类别顺序**（页面按此顺序渲染）：
`教师 → 博后 → 博士 → 硕士 → 本科 → 国内外合作伙伴 → 毕业生`

**照片要求**：正方形，建议 400×400px 以上，PNG 或 JPG，文件名全小写，上传到 `assets/img/people/`。

**毕业时**：将 `category` 改为 `毕业生`，填写 `join_date`（如 `2021-2024`），`research` 改为去向（如 `博士 at 宾大`），删除 `image`（留空即可）。

---

### 3. 添加论文

在 `_bibliography/papers.bib` **顶部**（最新的放最前）添加条目：

```bibtex
@inproceedings{zhong2025cvpr,
  abbr        = {CVPR},
  bibtex_show = {true},
  title       = {论文标题},
  author      = {Zhang, San and Li, Si and Zhong†, Zhun},
  booktitle   = {CVPR},
  year        = {2025},
  pdf         = {https://arxiv.org/abs/2501.xxxxx},
  code        = {https://github.com/xxx/xxx},
  preview     = {zhong2025cvpr.png},   % 可选：论文缩略图，放 assets/img/publication_preview/
  selected    = {false},               % true 则在主页展示，谨慎使用
}
```

期刊用 `@article` + `journal={}` 替换 `booktitle`。

**BibTeX key 规则**：`姓拼音+年份+会议小写`，全库唯一（如 `zhong2025cvpr`、`zhang2025neurips`）。

**`abbr` 常用值**（对应 `venues.yml` 中的颜色配置）：
`CVPR` · `ICCV` · `ECCV` · `NeurIPS` · `ICLR` · `ICML` · `AAAI` · `IJCAI` · `ACM MM` · `EMNLP` · `TPAMI` · `IJCV` · `ARXIV`

**`†` 通讯作者**：在作者名后加 `†`，如 `Zhong†, Zhun`。

**自动加作者链接**：在 `_data/coauthors.yml` 中为新成员添加映射：
```yaml
"zhang":
  - firstname: ["San", "S."]
    url: https://personal-website.com/
```

---

### 4. 修改主页（about.md）

直接编辑 `_pages/cn-cn/about.md`（**同步** `_pages/en-us/about.md`），内容为纯 Markdown。

frontmatter 中的关键字段（**不要改动**）：
```yaml
permalink: /        # 主页固定为根路径
news: true          # 显示新闻滚动栏
selected_papers: false
social: false
```

---

### 5. 修改招生信息（joinus.md）

编辑 `_pages/cn-cn/joinus.md`（**同步** `_pages/en-us/joinus.md`）。

重要通知用红色加粗：
```html
<span style="color: red; font-weight: bold;">2026年保研招生已开始，欢迎联系</span>
```

已关闭名额加删除线：
```html
<span style="color: red; font-weight: bold;"><del>2025年博士名额已满</del></span>
```

---

### 6. 更新论文作者链接

编辑 `_data/coauthors.yml`，新增合作者：
```yaml
"lastname":
  - firstname: ["全名", "缩写"]
    url: https://homepage.url/
```

key 是作者**姓的小写拼音/英文**，Jekyll Scholar 自动在论文列表中为匹配的作者名添加超链接。

---

## 不常用但重要的配置

### _config.yml 关键字段

```yaml
# 需要时更新（邮箱、Google Analytics 等）
email: zhunzhong007@gmail.com     # 联系邮箱
scholar_userid: qc6CJjYAAAAJ      # Google Scholar ID

# 控制主页新闻栏
announcements:
  limit: 10          # 主页显示的最新公告数

# 论文页配置
scholar:
  last_name: [Zhong]
  first_name: [Zhun, Z.]          # 高亮显示的作者名
  group_by: year
  group_order: descending
```

### 界面文字

`_data/cn-cn/strings.yml` 控制导航、页脚等界面文本，轻易不改。

---

## 核心约束

| 约束 | 说明 |
|------|------|
| **中英双语同步** | 每次改 `cn-cn/` 下的文件，**必须**同步改 `en-us/` 对应文件 |
| **不改主题核心** | 不修改 `_layouts/`、`_includes/`、`_sass/`、`_plugins/` |
| **_config.yml 谨慎改** | 全局配置影响整站，改前说明用途 |
| **照片文件名小写** | `assets/img/people/` 中文件名全小写，避免大小写报错 |
| **BibTeX key 唯一** | `papers.bib` 中每个条目 key 全局唯一 |
| **不维护 pt-br** | 葡萄牙语为上游示例，忽略即可 |

---

## 提交与部署

```bash
# 只 add 修改的具体文件，不要 git add .
git add _news/cn-cn/announcement_20250526.md _news/en-us/announcement_20250526.md
git commit -m "add news: ICCV 2025 两篇论文录用"
git push origin main
# GitHub Actions 自动构建，3-5 分钟后生效
```

**commit message 参考格式**：
- `add news: CVPR 2025 录用通知`
- `update profiles: 添加 2025 级硕士生`
- `update bib: 新增 ICCV 2025 两篇论文`
- `update joinus: 2026 年招生信息`
- `update about: 修改实验室简介`

---

## 本地预览（Docker）

本项目使用 Docker 进行本地预览，无需安装 Ruby/Jekyll/ImageMagick。

**前提**：已安装 [Docker Desktop for Mac（Apple Chip）](https://www.docker.com/products/docker-desktop/)，且 Docker 处于运行状态。

```bash
cd /Users/sky/LION-HFUT.github.io

# 首次运行：拉取镜像（约 400MB，仅需一次）
docker compose pull

# 启动本地预览（之后每次用这条）
docker compose up
```

出现 `Server running... port 8080` 后，浏览器打开 **http://localhost:8080**。

- 修改文件后页面**自动热更新**，无需重启
- 停止服务：`Ctrl+C`，然后 `docker compose down`
- 再次启动：直接 `docker compose up`（无需重新 pull）
