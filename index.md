---
layout: default
title: ARYX Guide - AI Tools, SEO Tips & Blogging for Beginners
description: Practical guides on AI tools, SEO strategies, blogging, and making money online. No fluff, just what works. Written by Aryx K.
---
<style>
.home-wrap { display:grid; grid-template-columns:1fr 280px; gap:24px; align-items:start; }
@media(max-width:960px){ .home-wrap { grid-template-columns:1fr; } }
</style>
<div class="home-wrap">
  <div>

    <!-- HERO: Latest Post - static for SEO -->
    <div class="hero-post reveal" id="hero-post">
      {% assign hero = site.posts | first %}
      {% if hero %}
      <a class="hero-card" href="{{ hero.url }}">
        <div class="hero-img">
          {% if hero.image %}<img src="{{ hero.image }}" alt="{{ hero.title }}" loading="eager"/>
          {% else %}<span style="font-size:48px;opacity:0.15;">⚡</span>{% endif %}
        </div>
        <div class="hero-body">
          <div class="hero-badge">
            <span class="hero-latest">Latest</span>
            {% if hero.categories[0] %}<span class="hero-cat">{{ hero.categories[0] }}</span>{% endif %}
          </div>
          <div class="hero-title">{{ hero.title }}</div>
          {% if hero.excerpt %}<div class="hero-excerpt">{{ hero.excerpt | strip_html | truncate: 150 }}</div>{% endif %}
          <div class="hero-meta"><span>📅 {{ hero.date | date: "%Y-%m-%d" }}</span></div>
          <div class="hero-read">Read Article →</div>
        </div>
      </a>
      {% endif %}
    </div>

    <!-- LATEST ARTICLES header -->
    <div class="sec-hdr reveal">
      <h2 class="sec-title">Latest Articles</h2>
      <div class="sec-line"></div>
      <span class="sec-tag">FRESH</span>
    </div>

    <!-- First 10 posts: static Jekyll — instant render, no JS needed -->
    <div class="grid2 reveal" id="posts-grid">
      {% for post in site.posts offset:1 limit:10 %}
      <a class="gcard reveal" href="{{ post.url }}">
        <div class="gc-img">
          {% if post.image %}<img src="{{ post.image }}" alt="{{ post.title }}" loading="lazy"/>
          {% else %}<span style="font-size:32px;opacity:0.2;">⚡</span>{% endif %}
        </div>
        <div class="gc-body">
          {% if post.categories[0] %}<span class="ctag">{{ post.categories[0] }}</span>{% endif %}
          <h3>{{ post.title }}</h3>
          <div class="cmeta"><span>{{ post.date | date: "%Y-%m-%d" }}</span><span class="cread">Read →</span></div>
        </div>
      </a>
      {% endfor %}
    </div>

    <div id="pagination-wrap">
      {% if site.posts.size > 11 %}
      <div class="load-wrap">
        <button class="load-btn" id="load-more-btn" onclick="renderBatch()"><span>Load More</span><span class="spinner"></span></button>
      </div>
      {% endif %}
    </div>

  </div>

  <!-- RIGHT COLUMN -->
  <div class="rcol">
    <div class="rcol-inner">
      <div class="wbox">
        <div class="wtitle">Popular Posts</div>
        <div class="pop-list" id="pop-list-home"></div>
      </div>
      <div class="wbox hero-widget">
        <div class="hw-eyebrow">⚡ ARYX Guide</div>
        <div class="hw-title">Level Up Your <span>Digital Game</span></div>
        <div class="hw-desc">AI tools, SEO strategies, blogging tips, and ways to make money online.</div>
        <a class="hw-btn" href="/">Explore →</a>
      </div>
      <div class="wbox">
        <div class="wtitle">Categories</div>
        <div class="cat-list" id="cat-list-home"></div>
      </div>
      <div class="wbox">
        <div class="wtitle">Archive</div>
        <div class="arc-list" id="arc-list-home"></div>
      </div>
    </div>
  </div>
</div>

<script>
// ALL_POSTS used only for: sidebar widgets + Load More (posts after index 11)
var ALL_POSTS = [
  {% for post in site.posts %}
  {
    "title": {{ post.title | jsonify }},
    "url": {{ post.url | jsonify }},
    "date": {{ post.date | date: "%Y-%m-%d" | jsonify }},
    "category": {{ post.categories | first | jsonify }},
    "image": {{ post.image | default: "" | jsonify }},
    "excerpt": {{ post.excerpt | strip_html | truncate: 150 | jsonify }}
  }{% unless forloop.last %},{% endunless %}
  {% endfor %}
];

// Load More — starts from index 11 (hero=0, static grid=1-10)
var LOAD_START = 11;
var PER_BATCH  = 10;
var _loaded    = 0;

function buildCard(p) {
  var img = p.image
    ? '<img src="' + p.image + '" alt="' + p.title.replace(/"/g, '&quot;') + '" loading="lazy"/>'
    : '<span style="font-size:32px;opacity:0.2;">⚡</span>';
  var cat = p.category ? '<span class="ctag">' + p.category + '</span>' : '';
  return '<a class="gcard reveal" href="' + p.url + '">'
    + '<div class="gc-img">' + img + '</div>'
    + '<div class="gc-body">' + cat
    + '<h3>' + p.title + '</h3>'
    + '<div class="cmeta"><span>' + p.date + '</span><span class="cread">Read →</span></div>'
    + '</div></a>';
}

function renderBatch() {
  var remaining = ALL_POSTS.slice(LOAD_START + _loaded);
  var batch = remaining.slice(0, PER_BATCH);
  if (batch.length === 0) return;

  var grid = document.getElementById('posts-grid');
  var html = '';
  for (var i = 0; i < batch.length; i++) html += buildCard(batch[i]);
  grid.innerHTML += html;
  _loaded += batch.length;
  if (typeof reObserveReveal === 'function') reObserveReveal();

  var wrap = document.getElementById('pagination-wrap');
  if (!wrap) return;
  if (LOAD_START + _loaded < ALL_POSTS.length) {
    wrap.innerHTML = '<div class="load-wrap"><button class="load-btn" id="load-more-btn" onclick="renderBatch()"><span>Load More</span><span class="spinner"></span></button></div>';
  } else {
    wrap.innerHTML = '';
  }
}

// Sidebar widgets
function loadSidebarWidgets() {
  var popHtml = '';
  ALL_POSTS.slice(0, 5).forEach(function(p, i) {
    popHtml += '<a class="pop-item" href="' + p.url + '"><div class="pop-num">0' + (i + 1) + '</div><div class="pop-text">' + p.title + '</div></a>';
  });
  var popEl = document.getElementById('pop-list-home');
  if (popEl) popEl.innerHTML = popHtml;

  var cats = {};
  ALL_POSTS.forEach(function(p) { if (p.category) cats[p.category] = (cats[p.category] || 0) + 1; });
  var SHOW_LABELS = ['AI Tools','SEO','Blogging','Make Money Online','Affiliate Marketing','Passive Income','Productivity','Automation','Content Writing','Social Media','YouTube','Freelancing'];
  var catHtml = '';
  SHOW_LABELS.forEach(function(name) {
    if (cats[name]) {
      catHtml += '<a class="cat-item" href="/category/' + name.toLowerCase().replace(/[^a-z0-9]+/g, '-').replace(/^-|-$/g, '') + '"><span class="cat-item-left">' + name + '</span><span class="cat-count">' + cats[name] + '</span></a>';
    }
  });
  var catEl = document.getElementById('cat-list-home');
  if (catEl && catHtml) catEl.innerHTML = catHtml;

  var months = {};
  var monthNames = ['','Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  ALL_POSTS.forEach(function(p) {
    if (p.date) { var ym = p.date.substring(0, 7); months[ym] = (months[ym] || 0) + 1; }
  });
  var arcHtml = '';
  Object.keys(months).sort().reverse().slice(0, 6).forEach(function(ym) {
    var parts = ym.split('-');
    arcHtml += '<a class="arc-item" href="/' + parts[0] + '/' + parts[1] + '/"><span>' + monthNames[parseInt(parts[1])] + ' ' + parts[0] + '</span><span class="arc-count">' + months[ym] + '</span></a>';
  });
  var arcEl = document.getElementById('arc-list-home');
  if (arcEl && arcHtml) arcEl.innerHTML = arcHtml;
}

document.addEventListener('DOMContentLoaded', function() {
  loadSidebarWidgets();
});
</script>
