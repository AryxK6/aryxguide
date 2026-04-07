---
layout: default
title: ARYX Guide · Tech, AI Tools, SEO & Blogging
description: Your go-to resource for AI tools, SEO tips, blogging guides, and making money online. Written by Aryx K.
---
<style>
.home-wrap { display:grid; grid-template-columns:1fr 280px; gap:24px; align-items:start; }
@media(max-width:960px){ .home-wrap { grid-template-columns:1fr; } }
</style>
<div class="home-wrap">
  <div>
    <!-- HERO: Latest Post (static Liquid for SEO) -->
    <div class="hero-post" id="hero-post">
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
    <!-- LATEST ARTICLES (static Liquid for SEO) -->
    <div class="sec-hdr">
      <h2 class="sec-title">Latest Articles</h2>
      <div class="sec-line"></div>
      <span class="sec-tag">FRESH</span>
    </div>
    <div class="grid2" id="posts-grid">
      {% assign rest_posts = site.posts | offset: 1 | limit: 8 %}
      {% for post in rest_posts %}
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
    <div id="pagination-wrap">
      {% if site.posts.size > 9 %}
      <div class="load-wrap"><button class="load-btn" id="load-more-btn" onclick="loadMorePosts()"><span>Load More</span><span class="spinner"></span></button></div>
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
// ---- POSTS DATA FROM JEKYLL ----
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
// ---- LOAD MORE (extends beyond initial 9 static posts) ----
var POSTS_PER_PAGE = 8;
var _currentPage = 1; // page 0 already rendered statically

function loadMorePosts(){
  var btn = document.getElementById('load-more-btn');
  if(btn) btn.classList.add('loading');
  setTimeout(function(){
    var grid = document.getElementById('posts-grid');
    var postsToShow = ALL_POSTS.slice(1);
    var start = _currentPage * POSTS_PER_PAGE;
    var end = start + POSTS_PER_PAGE;
    var slice = postsToShow.slice(start, end);
    var html = '';
    for(var i=0;i<slice.length;i++) html += buildPostCard(slice[i]);
    grid.innerHTML += html;
    _currentPage++;
    var wrap = document.getElementById('pagination-wrap');
    if(!wrap) return;
    if(end < postsToShow.length){
      wrap.innerHTML = '<div class="load-wrap"><button class="load-btn" id="load-more-btn" onclick="loadMorePosts()"><span>Load More</span><span class="spinner"></span></button></div>';
    } else {
      wrap.innerHTML = '';
    }
  }, 300);
}
function buildPostCard(p){
  var html = '<a class="gcard" href="'+p.url+'">';
  html += '<div class="gc-img">'+(p.image?'<img src="'+p.image+'" alt="'+p.title+'" loading="lazy"/>':'<span style="font-size:32px;opacity:0.2;">⚡</span>')+'</div>';
  html += '<div class="gc-body">';
  if(p.category) html += '<span class="ctag">'+p.category+'</span>';
  html += '<h3>'+p.title+'</h3>';
  html += '<div class="cmeta"><span>'+p.date+'</span><span class="cread">Read →</span></div>';
  html += '</div></a>';
  return html;
}
// ---- SIDEBAR WIDGETS ----
function loadSidebarWidgets(){
  var popHtml = '';
  ALL_POSTS.slice(0,5).forEach(function(p,i){
    popHtml += '<a class="pop-item" href="'+p.url+'"><div class="pop-num">0'+(i+1)+'</div><div class="pop-text">'+p.title+'</div></a>';
  });
  var popEl = document.getElementById('pop-list-home');
  if(popEl) popEl.innerHTML = popHtml;
  var cats = {};
  ALL_POSTS.forEach(function(p){ if(p.category){ cats[p.category]=(cats[p.category]||0)+1; } });
  var SHOW_LABELS = ['AI Tools','SEO','Blogging','Make Money Online','Affiliate Marketing','Passive Income','Productivity','Automation','Content Writing','Social Media','YouTube','Freelancing'];
  var catHtml = '';
  SHOW_LABELS.forEach(function(name){
    if(cats[name]){
      catHtml += '<a class="cat-item" href="/category/'+name.toLowerCase().replace(/[^a-z0-9]+/g,'-').replace(/^-|-$/g,'')+'"><span class="cat-item-left">'+name+'</span><span class="cat-count">'+cats[name]+'</span></a>';
    }
  });
  var catEl = document.getElementById('cat-list-home');
  if(catEl && catHtml) catEl.innerHTML = catHtml;
  var months = {};
  var monthNames = ['','Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  ALL_POSTS.forEach(function(p){
    if(p.date){ var ym=p.date.substring(0,7); months[ym]=(months[ym]||0)+1; }
  });
  var arcHtml = '';
  Object.keys(months).sort().reverse().slice(0,6).forEach(function(ym){
    var parts=ym.split('-');
    arcHtml += '<a class="arc-item" href="/'+parts[0]+'/'+parts[1]+'/"><span>'+monthNames[parseInt(parts[1])]+' '+parts[0]+'</span><span class="arc-count">'+months[ym]+'</span></a>';
  });
  var arcEl = document.getElementById('arc-list-home');
  if(arcEl && arcHtml) arcEl.innerHTML = arcHtml;
}
document.addEventListener('DOMContentLoaded', function(){
  loadSidebarWidgets();
});
</script>
