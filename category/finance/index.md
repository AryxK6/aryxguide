---
layout: default
title: "Personal Finance & Smart Money — ARYXGuide"
description: "Personal finance guides for everyday people. Budgeting, saving, online income, investing basics and building wealth from scratch."
permalink: /category/finance/
sitemap: false
niche: finance
---

<style>
.cat-page { padding: 32px 0 60px; }
.cat-eyebrow { display: flex; align-items: center; gap: 10px; margin-bottom: 14px; }
.cat-page-title { font-family: var(--font-head); font-size: clamp(26px,4vw,40px); font-weight: 700; letter-spacing: -0.5px; line-height: 1.15; color: var(--text); margin-bottom: 12px; }
.cat-page-desc { font-size: 15.5px; color: var(--text-2); line-height: 1.7; max-width: 680px; }
.subcat-grid { display: grid; grid-template-columns: repeat(4,1fr); gap: 10px; margin-bottom: 36px; }
.subcat-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius-md); padding: 14px; text-decoration: none; transition: border-color 0.2s, transform 0.2s; display: block; }
.subcat-card:hover { border-color: var(--pf-border); transform: translateY(-2px); }
.subcat-card-title { font-family: var(--font-head); font-size: 13px; font-weight: 700; color: var(--pf-primary); margin-bottom: 4px; }
.subcat-card-desc { font-size: 11px; color: var(--text-2); line-height: 1.5; }
.cat-divider { height: 1px; background: var(--divider); margin: 24px 0; }
@media(max-width:900px){ .subcat-grid { grid-template-columns: repeat(2,1fr); } }
@media(max-width:500px){ .subcat-grid { grid-template-columns: 1fr; } }
</style>

<div class="container cat-page">
  <div style="margin-bottom:32px;">
    <div class="cat-eyebrow"><span class="niche-pill pill-pf">Personal Finance</span></div>
    <h1 class="cat-page-title">Personal Finance & Smart Money</h1>
    <p class="cat-page-desc">Budgeting, saving, online income, investing basics and building wealth from scratch. Practical guides for everyday people with real money goals.</p>
  </div>

  <div class="subcat-grid">
    <a href="/category/finance/money-basics/" class="subcat-card"><div class="subcat-card-title">Money Basics</div><div class="subcat-card-desc">Literacy, management, emergency fund</div></a>
    <a href="/category/finance/budgeting-planning/" class="subcat-card"><div class="subcat-card-title">Budgeting & Planning</div><div class="subcat-card-desc">Monthly budget, 50/30/20, tracking</div></a>
    <a href="/category/finance/saving-money/" class="subcat-card"><div class="subcat-card-title">Saving Money</div><div class="subcat-card-desc">Daily habits, smart shopping, bills</div></a>
    <a href="/category/finance/student-finance/" class="subcat-card"><div class="subcat-card-title">Student Finance</div><div class="subcat-card-desc">Budget, scholarships, avoiding debt</div></a>
    <a href="/category/finance/online-income/" class="subcat-card"><div class="subcat-card-title">Online Income</div><div class="subcat-card-desc">Freelancing, AI tools, digital products</div></a>
    <a href="/category/finance/investing-basics/" class="subcat-card"><div class="subcat-card-title">Investing Basics</div><div class="subcat-card-desc">Mutual funds, compound interest</div></a>
    <a href="/category/finance/wealth-building/" class="subcat-card"><div class="subcat-card-title">Wealth Building</div><div class="subcat-card-desc">Net worth, multiple income, FIRE</div></a>
    <a href="/category/finance/money-mindset/" class="subcat-card"><div class="subcat-card-title">Money Mindset</div><div class="subcat-card-desc">Discipline, habits, financial freedom</div></a>
    <a href="/category/finance/tools-resources/" class="subcat-card"><div class="subcat-card-title">Tools & Resources</div><div class="subcat-card-desc">Apps, calculators, templates</div></a>
    <a href="/category/finance/digital-payments/" class="subcat-card"><div class="subcat-card-title">Digital Payments</div><div class="subcat-card-desc">Mobile pay, online banking, wallets</div></a>
  </div>

  <div class="cat-divider"></div>

  <div class="section-header" style="margin-top:0;">
    <div class="section-header-left">
      <div class="section-icon icon-pf"></div>
      <div class="section-title-wrap">
        <div class="section-title">All Finance Articles</div>
        <div class="section-desc">{{ site.finance | size }} articles published</div>
      </div>
    </div>
    <div class="section-line"></div>
  </div>

  {% assign pf_posts = site.finance | sort: 'date' | reverse %}
  {% if pf_posts.size > 0 %}
  <div class="cards-grid-3">
    {% for post in pf_posts %}
    <a href="{{ post.url }}" class="acard pf" style="text-decoration:none;">
      <div class="acard-img">{% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}</div>
      <div class="acard-body">
        {% assign pcat = post.categories | first | default: post.category %}
        {% if pcat %}<div class="niche-pill pill-pf" style="font-size:9px;margin-bottom:6px;">{{ pcat }}</div>{% endif %}
        <div class="acard-title">{{ post.title }}</div>
        {% if post.description %}<div class="acard-excerpt">{{ post.description }}</div>{% elsif post.excerpt %}<div class="acard-excerpt">{{ post.excerpt | strip_html | truncate: 110 }}</div>{% endif %}
        <div class="acard-foot"><span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span><span class="acard-read" style="color:var(--pf-primary);">Read →</span></div>
      </div>
    </a>
    {% endfor %}
  </div>
  {% else %}
  <div style="background:var(--pf-dim);border:1px solid var(--pf-border);border-radius:var(--radius-md);padding:32px;text-align:center;">
    <div style="font-family:var(--font-head);font-size:18px;font-weight:700;color:var(--text);margin-bottom:8px;">Articles Coming Soon</div>
    <div style="font-size:13px;color:var(--text-2);">Personal Finance guides are being published. Add articles to _finance/ folder.</div>
  </div>
  {% endif %}
</div>
