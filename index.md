---
layout: default
title: ARYX Guide · Tech, AI Tools, SEO & Blogging
description: Your go-to resource for AI tools, SEO tips, blogging guides, and making money online. Written by Aryx K.
---
<style>
/* Homepage specific */
.home-wrap { display:grid; grid-template-columns:1fr 280px; gap:24px; align-items:start; }
@media(max-width:960px){ .home-wrap { grid-template-columns:1fr; } }
</style>
<div class="home-wrap">
  <div>
    <!-- HERO: Latest Post -->
    <div class="hero-post" id="hero-post">
      <div style="padding:40px;text-align:center;color:var(--muted);font-size:12px;">Loading...</div>
    </div>
    <!-- LATEST ARTICLES -->
    <div class="sec-hdr">
      <h2 class="sec-title">Latest Articles</h2>
      <div class="sec-line"></div>
      <span class="sec-tag">FRESH</span>
    </div>
    <div class="grid2" id="posts-grid">
      <div style="grid-column:1/-1;text-align:center;padding:40px;color:var(--muted);font-size:12px;">Loading articles...</div>
    </div>
    <div id="pagination-wrap"></div>
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
// ---- HERO ----
function loadHeroPost(){
  var hero = document.getElementById('hero-post');
  if(!hero || ALL_POSTS.length === 0) return;
  var p = ALL_POSTS[0];
  var html = '<a class="hero-card" href="'+p.url+'">';
  html += '<div class="hero-img">';
  if(p.image){ html += '<img src="'+p.image+'" alt="'+p.title+'" loading="eager"/>'; }
  else { html += '<span style="font-size:48px;opacity:0.15;">⚡</span>'; }
  html += '</div>';
  html += '<div class="hero-body">';
  html += '<div class="hero-badge"><span class="hero-latest">Latest</span>';
  if(p.category){ html += '<span class="hero-cat">'+p.category+'</span>'; }
  html += '</div>';
  html += '<div class="hero-title">'+p.title+'</div>';
  if(p.excerpt){ html += '<div class="hero-excerpt">'+p.excerpt+'</div>'; }
  html += '<div class="hero-meta"><span>📅 '+p.date+'</span></div>';
  html += '<div class="hero-read">Read Article →</div>';
  html += '</div></a>';
  hero.innerHTML = html;
}
// ---- POSTS GRID ----
var POSTS_PER_PAGE = 8;
var _currentPage = 0;

function loadHomePosts(){
  var grid = document.getElementById('posts-grid');
  if(!grid) return;
  grid.innerHTML = '';
  showMorePosts();
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
function showMorePosts(){
  var grid = document.getElementById('posts-grid');
  if(!grid) return;
  var postsToShow = ALL_POSTS.slice(1); // Skip hero post
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
}
function loadMorePosts(){
  var btn = document.getElementById('load-more-btn');
  if(btn) btn.classList.add('loading');
  setTimeout(showMorePosts, 300);
}
// ---- SIDEBAR WIDGETS ----
function loadSidebarWidgets(){
  // Popular posts (latest 5)
  var popHtml = '';
  ALL_POSTS.slice(0,5).forEach(function(p,i){
    popHtml += '<a class="pop-item" href="'+p.url+'"><div class="pop-num">0'+(i+1)+'</div><div class="pop-text">'+p.title+'</div></a>';
  });
  document.getElementById('pop-list-home').innerHTML = popHtml;
  // Categories
  var cats = {};
  ALL_POSTS.forEach(function(p){ if(p.category){ cats[p.category]=(cats[p.category]||0)+1; } });
  var SHOW_LABELS = ['AI Tools','SEO','Blogging','Make Money Online','Affiliate Marketing','Passive Income','Productivity','Automation','Content Writing','Social Media','YouTube','Freelancing'];
  var catHtml = '';
  SHOW_LABELS.forEach(function(name){
    if(cats[name]){
      catHtml += '<a class="cat-item" href="/category/'+name.toLowerCase().replace(/[^a-z0-9]+/g,'-').replace(/^-|-$/g,'')+'"><span class="cat-item-left">'+name+'</span><span class="cat-count">'+cats[name]+'</span></a>';
    }
  });
  if(catHtml) document.getElementById('cat-list-home').innerHTML = catHtml;
  // Archive
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
  if(arcHtml) document.getElementById('arc-list-home').innerHTML = arcHtml;
}
document.addEventListener('DOMContentLoaded', function(){
  loadHeroPost();
  loadHomePosts();
  loadSidebarWidgets();
});
</script>
