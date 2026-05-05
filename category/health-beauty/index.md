---
layout: default
title: "Health & Beauty — Skin Care, Wellness, Hair Care & Natural DIY"
description: "All Health & Beauty articles. Skin care, hair care, wellness, women's health, natural DIY and honest product reviews."
permalink: /category/health-beauty/
sitemap: false
niche: health
---

<style>
.cat-page { padding: 32px 0 60px; }
.cat-header { margin-bottom: 32px; }
.cat-eyebrow { display: flex; align-items: center; gap: 10px; margin-bottom: 14px; }
.cat-page-title { font-family: var(--font-head); font-size: clamp(26px,4vw,40px); font-weight: 700; letter-spacing: -0.5px; line-height: 1.15; color: var(--text); margin-bottom: 12px; }
.cat-page-desc { font-size: 15.5px; color: var(--text-2); line-height: 1.7; max-width: 680px; }
.subcat-grid { display: grid; grid-template-columns: repeat(4,1fr); gap: 10px; margin-bottom: 36px; }
.subcat-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius-md); padding: 14px; text-decoration: none; transition: border-color 0.2s, transform 0.2s; display: block; }
.subcat-card:hover { border-color: var(--hb-border); transform: translateY(-2px); }
.subcat-card-title { font-family: var(--font-head); font-size: 13px; font-weight: 700; color: var(--hb-primary); margin-bottom: 4px; }
.subcat-card-desc { font-size: 11px; color: var(--text-2); line-height: 1.5; }
.cat-divider { height: 1px; background: var(--divider); margin: 24px 0; }
@media(max-width:900px){ .subcat-grid { grid-template-columns: repeat(2,1fr); } }
@media(max-width:500px){ .subcat-grid { grid-template-columns: 1fr; } }
</style>

<div class="container cat-page">
  <div class="cat-header">
    <div class="cat-eyebrow"><span class="niche-pill pill-hb">🌸 Health & Beauty</span></div>
    <h1 class="cat-page-title">Health & Beauty</h1>
    <p class="cat-page-desc">Skin care routines, hair care guides, wellness habits and honest product reviews. Written for real people, not influencers. No sponsored bias, no inflated ratings.</p>
  </div>

  <div class="subcat-grid">
    <a href="/category/health-beauty/skin-care/" class="subcat-card"><div class="subcat-card-title">💆 Skin Care</div><div class="subcat-card-desc">Routines, anti-aging, acne, serums</div></a>
    <a href="/category/health-beauty/hair-care/" class="subcat-card"><div class="subcat-card-title">💇 Hair Care</div><div class="subcat-card-desc">Growth, treatments, styling</div></a>
    <a href="/category/health-beauty/health-wellness/" class="subcat-card"><div class="subcat-card-title">🥗 Health & Wellness</div><div class="subcat-card-desc">Mental health, nutrition, sleep</div></a>
    <a href="/category/health-beauty/womens-health/" class="subcat-card"><div class="subcat-card-title">🌺 Women's Health</div><div class="subcat-card-desc">Hormonal, PCOS, pregnancy</div></a>
    <a href="/category/health-beauty/body-care/" class="subcat-card"><div class="subcat-card-title">🧴 Body Care</div><div class="subcat-card-desc">Body skin, weight, fitness</div></a>
    <a href="/category/health-beauty/makeup-beauty/" class="subcat-card"><div class="subcat-card-title">💄 Makeup & Beauty</div><div class="subcat-card-desc">Tips, hacks, nail care</div></a>
    <a href="/category/health-beauty/natural-diy/" class="subcat-card"><div class="subcat-card-title">🌿 Natural & DIY</div><div class="subcat-card-desc">Face masks, home remedies, oils</div></a>
    <a href="/category/health-beauty/product-reviews/" class="subcat-card"><div class="subcat-card-title">⭐ Product Reviews</div><div class="subcat-card-desc">Skin care, hair, supplements</div></a>
  </div>

  <div class="cat-divider"></div>

  <div class="section-header" style="margin-top:0;">
    <div class="section-header-left">
      <div class="section-icon icon-hb">🌸</div>
      <div class="section-title-wrap">
        <div class="section-title">All Health & Beauty Articles</div>
        <div class="section-desc">{{ site.health_beauty | size }} articles published</div>
      </div>
    </div>
    <div class="section-line"></div>
  </div>

  {% assign hb_posts = site.health_beauty | sort: 'date' | reverse %}
  {% if hb_posts.size > 0 %}
  <div class="cards-grid-3">
    {% for post in hb_posts %}
    <a href="{{ post.url }}" class="acard hb" style="text-decoration:none;">
      <div class="acard-img">{% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}</div>
      <div class="acard-body">
        {% assign hcat = post.categories | first | default: post.category %}
        {% if hcat %}<div class="niche-pill pill-hb" style="font-size:9px;margin-bottom:6px;">{{ hcat }}</div>{% endif %}
        <div class="acard-title">{{ post.title }}</div>
        {% if post.description %}<div class="acard-excerpt">{{ post.description }}</div>{% elsif post.excerpt %}<div class="acard-excerpt">{{ post.excerpt | strip_html | truncate: 110 }}</div>{% endif %}
        <div class="acard-foot"><span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span><span class="acard-read" style="color:var(--hb-primary);">Read →</span></div>
      </div>
    </a>
    {% endfor %}
  </div>
  {% else %}
  <div style="background:var(--hb-dim);border:1px solid var(--hb-border);border-radius:var(--radius-md);padding:32px;text-align:center;">
    <div style="font-size:36px;margin-bottom:12px;">🌸</div>
    <div style="font-family:var(--font-head);font-size:18px;font-weight:700;color:var(--text);margin-bottom:8px;">Articles Coming Soon</div>
    <div style="font-size:13px;color:var(--text-2);">Health & Beauty guides are being published regularly.</div>
  </div>
  {% endif %}
</div>
