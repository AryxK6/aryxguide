---
layout: default
title: "Digital Guide — AI Tools, SEO, Blogging & Make Money Online"
description: "All Digital Guide articles. AI tools, SEO, blogging, content creation, make money online, marketing and productivity guides."
permalink: /category/digital-guide/
sitemap: false
niche: ai
---

<style>
.cat-page { padding: 32px 0 60px; }
.cat-header { margin-bottom: 32px; }
.cat-eyebrow { display: flex; align-items: center; gap: 10px; margin-bottom: 14px; }
.cat-page-title { font-family: var(--font-head); font-size: clamp(26px,4vw,40px); font-weight: 700; letter-spacing: -0.5px; line-height: 1.15; color: var(--text); margin-bottom: 12px; }
.cat-page-desc { font-size: 15.5px; color: var(--text-2); line-height: 1.7; max-width: 680px; }
.subcat-grid { display: grid; grid-template-columns: repeat(5,1fr); gap: 10px; margin-bottom: 36px; }
.subcat-card { background: var(--bg-card); border: 1px solid var(--border); border-radius: var(--radius-md); padding: 14px; text-decoration: none; transition: border-color 0.2s, transform 0.2s; display: block; }
.subcat-card:hover { border-color: var(--ai-border); transform: translateY(-2px); }
.subcat-card-title { font-family: var(--font-head); font-size: 13px; font-weight: 700; color: var(--ai-primary); margin-bottom: 4px; }
.subcat-card-desc { font-size: 11px; color: var(--text-2); line-height: 1.5; }
.cat-divider { height: 1px; background: var(--divider); margin: 24px 0; }
@media(max-width:900px){ .subcat-grid { grid-template-columns: repeat(3,1fr); } }
@media(max-width:500px){ .subcat-grid { grid-template-columns: repeat(2,1fr); } }
</style>

<div class="container cat-page">
  <div class="cat-header">
    <div class="cat-eyebrow"><span class="niche-pill pill-ai">⚡ Digital Guide</span></div>
    <h1 class="cat-page-title">Digital Guide</h1>
    <p class="cat-page-desc">AI tools, SEO, blogging, content creation, make money online, marketing and productivity. Practical guides written from experience, not theory.</p>
  </div>

  <div class="subcat-grid">
    <a href="/category/digital-guide/ai-tools/" class="subcat-card"><div class="subcat-card-title">⚡ AI Tools</div><div class="subcat-card-desc">Guides, tutorials, image & video</div></a>
    <a href="/category/digital-guide/make-money-online/" class="subcat-card"><div class="subcat-card-title">💰 Make Money</div><div class="subcat-card-desc">Affiliate, products, passive income</div></a>
    <a href="/category/digital-guide/blogging-seo/" class="subcat-card"><div class="subcat-card-title">📈 Blogging & SEO</div><div class="subcat-card-desc">SEO, technical, content writing</div></a>
    <a href="/category/digital-guide/marketing-social/" class="subcat-card"><div class="subcat-card-title">📱 Marketing</div><div class="subcat-card-desc">Social media, email, YouTube</div></a>
    <a href="/category/digital-guide/productivity-business/" class="subcat-card"><div class="subcat-card-title">⚙️ Productivity</div><div class="subcat-card-desc">Automation, business, research</div></a>
  </div>

  <div class="cat-divider"></div>

  <div class="section-header" style="margin-top:0;">
    <div class="section-header-left">
      <div class="section-icon icon-ai">⚡</div>
      <div class="section-title-wrap">
        <div class="section-title">All Digital Guide Articles</div>
        <div class="section-desc">{{ site.posts | size }} articles published</div>
      </div>
    </div>
    <div class="section-line"></div>
  </div>

  <div class="cards-grid-3">
    {% assign all_posts = site.posts | sort: 'date' | reverse %}
    {% for post in all_posts %}
    <a href="{{ post.url }}" class="acard ai" style="text-decoration:none;">
      <div class="acard-img">{% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}</div>
      <div class="acard-body">
        {% assign pcat = post.categories | first %}
        {% if pcat %}<div class="niche-pill pill-ai" style="font-size:9px;margin-bottom:6px;">{{ pcat }}</div>{% endif %}
        <div class="acard-title">{{ post.title }}</div>
        {% if post.description %}<div class="acard-excerpt">{{ post.description }}</div>{% elsif post.excerpt %}<div class="acard-excerpt">{{ post.excerpt | strip_html | truncate: 110 }}</div>{% endif %}
        <div class="acard-foot"><span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span><span class="acard-read">Read →</span></div>
      </div>
    </a>
    {% endfor %}
  </div>
</div>
