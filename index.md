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

    <!-- HERO -->
    <div class="hero-post">
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

    <!-- SECTION HEADER -->
    <div class="sec-hdr">
      <h2 class="sec-title">Latest Articles</h2>
      <div class="sec-line"></div>
      <span class="sec-tag">FRESH</span>
    </div>

    <!-- FIRST 10 POSTS — pure Jekyll, no JS -->
    <div class="grid2" id="posts-grid">
      {% for post in site.posts offset:1 limit:10 %}
      <a class="gcard" href="{{ post.url }}">
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

    {% if site.posts.size > 11 %}
    <div id="pagination-wrap">
      <div class="load-wrap">
        <button class="load-btn" id="load-more-btn" onclick="loadMore()"><span>Load More</span><span class="spinner"></span></button>
      </div>
    </div>
    {% endif %}

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
var _allPosts = null;   // fetched once on first Load More click
var _loaded   = 0;     // how many extra posts rendered via JS (after the static 10)
var PER_BATCH = 10;
var STATIC_COUNT = 10; // posts already in DOM (offset:1 limit:10)

function buildCard(p) {
  var img = p.image
    ? '<img src="'+p.image+'" alt="'+p.title.replace(/"/g,'&quot;')+'" loading="lazy"/>'
    : '<span style="font-size:32px;opacity:0.2;">⚡</span>';
  var cat = p.category ? '<span class="ctag">'+p.category+'</span>' : '';
  return '<a class="gcard" href="'+p.url+'">'
    +'<div class="gc-img">'+img+'</div>'
    +'<div class="gc-body">'+cat
    +'<h3>'+p.title+'</h3>'
    +'<div class="cmeta"><span>'+p.date+'</span><span class="cread">Read →</span></div>'
    +'</div></a>';
}

function renderBatch(posts) {
  var grid = document.getElementById('posts-grid');
  var start = STATIC_COUNT + _loaded;        // skip hero(0) + static(1-10)
  var batch = posts.slice(start, start + PER_BATCH);
  if (!batch.length) { document.getElementById('pagination-wrap').innerHTML = ''; return; }

  var html = '';
  for (var i = 0; i < batch.length; i++) html += buildCard(batch[i]);
  grid.innerHTML += html;
  _loaded += batch.length;
  if (typeof reObserveReveal === 'function') reObserveReveal();

  var wrap = document.getElementById('pagination-wrap');
  if (start + PER_BATCH < posts.length) {
    wrap.innerHTML = '<div class="load-wrap"><button class="load-btn" id="load-more-btn" onclick="loadMore()"><span>Load More</span><span class="spinner"></span></button></div>';
  } else {
    wrap.innerHTML = '';
  }
}

function loadMore() {
  var btn = document.getElementById('load-more-btn');
  if (btn) btn.classList.add('loading');

  if (_allPosts) {
    renderBatch(_allPosts);
    return;
  }

  // Fetch search.json only once
  fetch('/search.json')
    .then(function(r) { return r.json(); })
    .then(function(data) {
      _allPosts = data;
      renderBatch(_allPosts);
    })
    .catch(function() {
      if (btn) btn.classList.remove('loading');
    });
}

// Sidebar — also uses search.json, fetched lazily
function loadSidebarWidgets() {
  fetch('/search.json')
    .then(function(r) { return r.json(); })
    .then(function(posts) {
      _allPosts = posts; // cache for Load More too

      // Popular Posts
      var popHtml = '';
      posts.slice(0,5).forEach(function(p,i){
        popHtml += '<a class="pop-item" href="'+p.url+'"><div class="pop-num">0'+(i+1)+'</div><div class="pop-text">'+p.title+'</div></a>';
      });
      var popEl = document.getElementById('pop-list-home');
      if (popEl) popEl.innerHTML = popHtml;

      // Categories
      var cats = {};
      posts.forEach(function(p){ if(p.category) cats[p.category]=(cats[p.category]||0)+1; });
      var LABELS = ['AI Tools','SEO','Blogging','Make Money Online','Affiliate Marketing','Passive Income','Productivity','Automation','Content Writing','Social Media','YouTube','Freelancing'];
      var catHtml = '';
      LABELS.forEach(function(name){
        if(cats[name]) catHtml += '<a class="cat-item" href="/category/'+name.toLowerCase().replace(/[^a-z0-9]+/g,'-').replace(/^-|-$/g,'')+'"><span class="cat-item-left">'+name+'</span><span class="cat-count">'+cats[name]+'</span></a>';
      });
      var catEl = document.getElementById('cat-list-home');
      if (catEl && catHtml) catEl.innerHTML = catHtml;

      // Archive
      var months = {};
      var mNames = ['','Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
      posts.forEach(function(p){ if(p.date){ var ym=p.date.substring(0,7); months[ym]=(months[ym]||0)+1; } });
      var arcHtml = '';
      Object.keys(months).sort().reverse().slice(0,6).forEach(function(ym){
        var pts=ym.split('-');
        arcHtml += '<a class="arc-item" href="/'+pts[0]+'/'+pts[1]+'/"><span>'+mNames[parseInt(pts[1])]+' '+pts[0]+'</span><span class="arc-count">'+months[ym]+'</span></a>';
      });
      var arcEl = document.getElementById('arc-list-home');
      if (arcEl && arcHtml) arcEl.innerHTML = arcHtml;
    })
    .catch(function(){});
}

document.addEventListener('DOMContentLoaded', loadSidebarWidgets);
</script>
