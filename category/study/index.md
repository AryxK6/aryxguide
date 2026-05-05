---
layout: default
title: "Study — Career, Certifications, Skills & Student Success"
description: "All Study articles. Career guidance, certifications, digital skills, freelancing, personal growth and student life guides."
permalink: /category/study/
sitemap: false
niche: study
---

<style>
.cat-page { padding: 32px 0 60px; }
.cat-header { margin-bottom: 32px; }
.cat-eyebrow { display: flex; align-items: center; gap: 10px; margin-bottom: 14px; }
.cat-page-title { font-family: var(--font-head); font-size: clamp(26px,4vw,40px); font-weight: 700; letter-spacing: -0.5px; line-height: 1.15; color: var(--text); margin-bottom: 12px; }
.cat-page-desc { font-size: 15.5px; color: var(--text-2); line-height: 1.7; max-width: 680px; }
.subcat-grid { display: grid; grid-template-columns: repeat(5,1fr); gap: 10px; margin-bottom: 36px; }
.subcat-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius-md); padding: 14px; text-decoration: none; transition: border-color 0.2s, transform 0.2s; display: block; }
.subcat-card:hover { border-color: var(--st-border); transform: translateY(-2px); }
.subcat-card-title { font-family: var(--font-head); font-size: 13px; font-weight: 700; color: var(--st-primary); margin-bottom: 4px; }
.subcat-card-desc { font-size: 11px; color: var(--text-2); line-height: 1.5; }
.cat-divider { height: 1px; background: var(--divider); margin: 24px 0; }
@media(max-width:900px){ .subcat-grid { grid-template-columns: repeat(3,1fr); } }
@media(max-width:500px){ .subcat-grid { grid-template-columns: repeat(2,1fr); } }
</style>

<div class="container cat-page">
  <div class="cat-header">
    <div class="cat-eyebrow"><span class="niche-pill pill-st">📚 Study</span></div>
    <h1 class="cat-page-title">Study & Career</h1>
    <p class="cat-page-desc">Career guidance, certifications, digital skills, freelancing and personal growth guides. Practical content for students and early-career professionals.</p>
  </div>

  <div class="subcat-grid">
    <a href="/category/study/study-tips/" class="subcat-card"><div class="subcat-card-title">🧠 Study Tips</div><div class="subcat-card-desc">Time, focus, note-taking, exams</div></a>
    <a href="/category/study/career-guidance/" class="subcat-card"><div class="subcat-card-title">💼 Career</div><div class="subcat-card-desc">Resume, interviews, LinkedIn</div></a>
    <a href="/category/study/certifications/" class="subcat-card"><div class="subcat-card-title">🏆 Certifications</div><div class="subcat-card-desc">Google, Meta, AWS, free certs</div></a>
    <a href="/category/study/online-courses/" class="subcat-card"><div class="subcat-card-title">🎓 Courses</div><div class="subcat-card-desc">Coursera, Udemy, edX guides</div></a>
    <a href="/category/study/freelancing-remote/" class="subcat-card"><div class="subcat-card-title">💻 Freelancing</div><div class="subcat-card-desc">Platforms, pricing, clients</div></a>
    <a href="/category/study/personal-growth/" class="subcat-card"><div class="subcat-card-title">🌱 Personal Growth</div><div class="subcat-card-desc">Goals, habits, confidence</div></a>
    <a href="/category/study/digital-skills/" class="subcat-card"><div class="subcat-card-title">⚡ Digital Skills</div><div class="subcat-card-desc">AI tools, design, coding</div></a>
    <a href="/category/study/college-student-life/" class="subcat-card"><div class="subcat-card-title">🎒 College Life</div><div class="subcat-card-desc">Degrees, scholarships, budget</div></a>
    <a href="/category/study/language-communication/" class="subcat-card"><div class="subcat-card-title">🗣️ Language</div><div class="subcat-card-desc">English, communication, writing</div></a>
    <a href="/category/study/tools-resources/" class="subcat-card"><div class="subcat-card-title">🛠️ Tools</div><div class="subcat-card-desc">Apps, design tools, learning sites</div></a>
  </div>

  <div class="cat-divider"></div>

  <div class="section-header" style="margin-top:0;">
    <div class="section-header-left">
      <div class="section-icon icon-st">📚</div>
      <div class="section-title-wrap">
        <div class="section-title">All Study Articles</div>
        <div class="section-desc">{{ site.study | size }} articles published</div>
      </div>
    </div>
    <div class="section-line"></div>
  </div>

  {% assign st_posts = site.study | sort: 'date' | reverse %}
  {% if st_posts.size > 0 %}
  <div class="cards-grid-3">
    {% for post in st_posts %}
    <a href="{{ post.url }}" class="acard st" style="text-decoration:none;">
      <div class="acard-img">{% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}</div>
      <div class="acard-body">
        {% assign scat = post.categories | first | default: post.category %}
        {% if scat %}<div class="niche-pill pill-st" style="font-size:9px;margin-bottom:6px;">{{ scat }}</div>{% endif %}
        <div class="acard-title">{{ post.title }}</div>
        {% if post.description %}<div class="acard-excerpt">{{ post.description }}</div>{% elsif post.excerpt %}<div class="acard-excerpt">{{ post.excerpt | strip_html | truncate: 110 }}</div>{% endif %}
        <div class="acard-foot"><span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span><span class="acard-read" style="color:var(--st-primary);">Read →</span></div>
      </div>
    </a>
    {% endfor %}
  </div>
  {% else %}
  <div style="background:var(--st-dim);border:1px solid var(--st-border);border-radius:var(--radius-md);padding:32px;text-align:center;">
    <div style="font-size:36px;margin-bottom:12px;">📚</div>
    <div style="font-family:var(--font-head);font-size:18px;font-weight:700;color:var(--text);margin-bottom:8px;">Articles Coming Soon</div>
    <div style="font-size:13px;color:var(--text-2);">Study and career guides are being published regularly.</div>
  </div>
  {% endif %}
</div>
