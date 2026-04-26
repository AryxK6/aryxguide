---
layout: default
title: ARYXGuide — AI Tools, Health & Beauty, Study Guides
description: Practical guides on AI tools, health & beauty, and study tips. Real content, tested strategies, no filler.
permalink: /
sitemap: true
---

<div class="container" style="padding-bottom:60px;">

  <!-- ═══════════════════════════════════════
       HERO GRID
  ═══════════════════════════════════════ -->
  <div class="hero-strip">
    {% assign latest_ai = site.posts | sort: 'date' | reverse %}
    {% assign latest_hb = site.health_beauty | sort: 'date' | reverse %}
    {% assign latest_st = site.study | sort: 'date' | reverse %}
    {% assign hero_post = latest_ai | first %}
    {% assign side1 = latest_hb | first %}
    {% assign side2 = latest_st | first %}

    <div class="hero-grid">
      <!-- Main featured — latest AI post -->
      {% if hero_post %}
      <a href="{{ hero_post.url }}" class="hero-main" style="text-decoration:none;">
        {% if hero_post.image %}
        <img src="{{ hero_post.image }}" alt="{{ hero_post.image_alt | default: hero_post.title }}" loading="eager"/>
        {% endif %}
        <div class="hero-main-body">
          <div class="niche-pill pill-ai">⚡ AI Guide</div>
          <div class="article-title">{{ hero_post.title }}</div>
          <div class="article-meta" style="color:rgba(255,255,255,0.5);">
            <span>Aryx K.</span><span class="sep">·</span>
            <span>{{ hero_post.date | date: "%b %d, %Y" }}</span>
          </div>
          <div class="read-more" style="color:var(--ai-light);">Read Article →</div>
        </div>
      </a>
      {% endif %}

      <!-- Side 1 — latest Health post -->
      {% if side1 %}
      <a href="{{ side1.url }}" class="hero-side" style="text-decoration:none;">
        <div>
          <div class="niche-pill pill-hb">🌸 Health & Beauty</div>
          <div class="article-title">{{ side1.title }}</div>
          <div class="article-meta">
            <span>Aryx K.</span><span class="sep">·</span>
            <span>{{ side1.date | date: "%b %d, %Y" }}</span>
          </div>
        </div>
        <div class="read-more" style="color:var(--hb-primary);">Read →</div>
      </a>
      {% else %}
      <div class="hero-side" style="justify-content:center;align-items:center;text-align:center;">
        <div style="opacity:0.4;">
          <div style="font-size:32px;margin-bottom:8px;">🌸</div>
          <div style="font-size:13px;color:var(--text-3);">Health & Beauty<br>articles coming soon</div>
        </div>
      </div>
      {% endif %}

      <!-- Side 2 — latest Study post -->
      {% if side2 %}
      <a href="{{ side2.url }}" class="hero-side" style="text-decoration:none;">
        <div>
          <div class="niche-pill pill-st">📚 Study</div>
          <div class="article-title">{{ side2.title }}</div>
          <div class="article-meta">
            <span>Aryx K.</span><span class="sep">·</span>
            <span>{{ side2.date | date: "%b %d, %Y" }}</span>
          </div>
        </div>
        <div class="read-more" style="color:var(--st-primary);">Read →</div>
      </a>
      {% else %}
      <div class="hero-side" style="justify-content:center;align-items:center;text-align:center;">
        <div style="opacity:0.4;">
          <div style="font-size:32px;margin-bottom:8px;">📚</div>
          <div style="font-size:13px;color:var(--text-3);">Study articles<br>coming soon</div>
        </div>
      </div>
      {% endif %}
    </div>
  </div>

  <!-- ═══════════════════════════════════════
       AI GUIDE — Latest 3
  ═══════════════════════════════════════ -->
  <div class="reveal" style="margin-bottom:52px;">
    <div class="section-header">
      <div class="section-header-left">
        <div class="section-icon icon-ai">⚡</div>
        <div class="section-title-wrap">
          <div class="section-title">AI Guide</div>
          <div class="section-desc">Tools, SEO, blogging & ways to make money online</div>
        </div>
      </div>
      <div class="section-line"></div>
      <a href="/category/ai-guides/" class="section-view-all ai">View All →</a>
    </div>
    <div class="cards-grid-4">
      {% for post in latest_ai limit: 4 %}
      <a href="{{ post.url }}" class="acard ai" style="text-decoration:none;">
        <div class="acard-img">
          {% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}
        </div>
        <div class="acard-body">
          {% assign cat = post.categories | first %}
          {% if cat %}<div class="niche-pill pill-ai" style="font-size:9px;margin-bottom:6px;">{{ cat }}</div>{% endif %}
          <div class="acard-title">{{ post.title }}</div>
          {% if post.description %}<div class="acard-excerpt">{{ post.description }}</div>
          {% elsif post.excerpt %}<div class="acard-excerpt">{{ post.excerpt | strip_html | truncate: 110 }}</div>{% endif %}
          <div class="acard-foot">
            <span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span>
            <span class="acard-read">Read →</span>
          </div>
        </div>
      </a>
      {% endfor %}
    </div>
  </div>

  <!-- ═══════════════════════════════════════
       HEALTH & BEAUTY — Latest 3
  ═══════════════════════════════════════ -->
  <div class="reveal" style="margin-bottom:52px;">
    <div class="section-header">
      <div class="section-header-left">
        <div class="section-icon icon-hb">🌸</div>
        <div class="section-title-wrap">
          <div class="section-title">Health & Beauty</div>
          <div class="section-desc">Skin care, wellness, hair care & natural DIY</div>
        </div>
      </div>
      <div class="section-line"></div>
      <a href="/health-beauty/" class="section-view-all hb">View All →</a>
    </div>

    {% if latest_hb.size > 0 %}
    <div class="cards-grid-3">
      {% for post in latest_hb limit: 3 %}
      <a href="{{ post.url }}" class="acard hb" style="text-decoration:none;">
        <div class="acard-img">
          {% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}
        </div>
        <div class="acard-body">
          {% assign hcat = post.categories | first | default: post.category %}
          {% if hcat %}<div class="niche-pill pill-hb" style="font-size:9px;margin-bottom:6px;">{{ hcat }}</div>{% endif %}
          <div class="acard-title">{{ post.title }}</div>
          {% if post.description %}<div class="acard-excerpt">{{ post.description }}</div>
          {% elsif post.excerpt %}<div class="acard-excerpt">{{ post.excerpt | strip_html | truncate: 110 }}</div>{% endif %}
          <div class="acard-foot">
            <span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span>
            <span class="acard-read" style="color:var(--hb-primary);">Read →</span>
          </div>
        </div>
      </a>
      {% endfor %}
    </div>
    {% else %}
    <div style="background:var(--hb-dim);border:1px solid var(--hb-border);border-radius:var(--radius-md);padding:32px;text-align:center;">
      <div style="font-size:36px;margin-bottom:12px;">🌸</div>
      <div style="font-family:var(--font-head);font-size:18px;font-weight:700;color:var(--text);margin-bottom:8px;">Health & Beauty Articles Coming Soon</div>
      <div style="font-size:13px;color:var(--text-2);line-height:1.6;">Skin care, hair care, wellness and natural DIY guides are being published. Add MD files to <code>_health_beauty/</code> folder.</div>
    </div>
    {% endif %}
  </div>

  <!-- ═══════════════════════════════════════
       STUDY — Latest 3
  ═══════════════════════════════════════ -->
  <div class="reveal" style="margin-bottom:52px;">
    <div class="section-header">
      <div class="section-header-left">
        <div class="section-icon icon-st">📚</div>
        <div class="section-title-wrap">
          <div class="section-title">Study</div>
          <div class="section-desc">Career, certifications, skills & student success</div>
        </div>
      </div>
      <div class="section-line"></div>
      <a href="/study/" class="section-view-all st">View All →</a>
    </div>

    {% if latest_st.size > 0 %}
    <div class="cards-grid-3">
      {% for post in latest_st limit: 3 %}
      <a href="{{ post.url }}" class="acard st" style="text-decoration:none;">
        <div class="acard-img">
          {% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}
        </div>
        <div class="acard-body">
          {% assign scat = post.categories | first | default: post.category %}
          {% if scat %}<div class="niche-pill pill-st" style="font-size:9px;margin-bottom:6px;">{{ scat }}</div>{% endif %}
          <div class="acard-title">{{ post.title }}</div>
          {% if post.description %}<div class="acard-excerpt">{{ post.description }}</div>
          {% elsif post.excerpt %}<div class="acard-excerpt">{{ post.excerpt | strip_html | truncate: 110 }}</div>{% endif %}
          <div class="acard-foot">
            <span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span>
            <span class="acard-read" style="color:var(--st-primary);">Read →</span>
          </div>
        </div>
      </a>
      {% endfor %}
    </div>
    {% else %}
    <div style="background:var(--st-dim);border:1px solid var(--st-border);border-radius:var(--radius-md);padding:32px;text-align:center;">
      <div style="font-size:36px;margin-bottom:12px;">📚</div>
      <div style="font-family:var(--font-head);font-size:18px;font-weight:700;color:var(--text);margin-bottom:8px;">Study Articles Coming Soon</div>
      <div style="font-size:13px;color:var(--text-2);line-height:1.6;">Career, certifications, and digital skills guides are being published. Add MD files to <code>_study/</code> folder.</div>
    </div>
    {% endif %}
  </div>

  <!-- ═══════════════════════════════════════
       MORE AI — Next 3 (posts 4-6)
  ═══════════════════════════════════════ -->
  {% assign more_ai = latest_ai | offset: 3 %}
  {% if more_ai.size > 0 %}
  <div class="reveal" style="margin-bottom:52px;">
    <div class="section-header">
      <div class="section-header-left">
        <div class="section-icon icon-ai">🔥</div>
        <div class="section-title-wrap">
          <div class="section-title">More AI Guides</div>
          <div class="section-desc">Recently published</div>
        </div>
      </div>
      <div class="section-line"></div>
      <a href="/category/ai-guides/" class="section-view-all ai">All Posts →</a>
    </div>
    <div class="cards-grid-4">
      {% for post in more_ai limit: 4 %}
      <a href="{{ post.url }}" class="acard ai" style="text-decoration:none;">
        <div class="acard-img">
          {% if post.image %}<img src="{{ post.image }}" alt="{{ post.image_alt | default: post.title }}" loading="lazy"/>{% endif %}
        </div>
        <div class="acard-body">
          {% assign cat2 = post.categories | first %}
          {% if cat2 %}<div class="niche-pill pill-ai" style="font-size:9px;margin-bottom:6px;">{{ cat2 }}</div>{% endif %}
          <div class="acard-title">{{ post.title }}</div>
          <div class="acard-foot">
            <span class="acard-date">{{ post.date | date: "%b %d, %Y" }}</span>
            <span class="acard-read">Read →</span>
          </div>
        </div>
      </a>
      {% endfor %}
    </div>
  </div>
  {% endif %}

</div>
