---
layout: default
title: "Research"
description: "Articles and guides about Research."
permalink: /category/research
---
<style>
.cat-page-hero{background:linear-gradient(135deg,var(--bg-card),var(--neon-dim));border-bottom:1px solid var(--border);padding:3rem 1.5rem;text-align:center;margin:-16px -16px 32px;}
.cat-page-hero h1{font-family:'Syne',sans-serif;font-size:clamp(1.8rem,4vw,2.5rem);font-weight:800;margin-bottom:0.5rem;}
.cat-page-hero h1 span{color:var(--neon);text-shadow:var(--neon-glow);}
.cat-page-hero p{color:var(--text2);font-size:1rem;}
.sub-cats{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:28px;}
.sub-cat-link{background:var(--tag-bg);border:1px solid var(--border);color:var(--neon);padding:6px 14px;border-radius:20px;text-decoration:none;font-size:0.85rem;font-family:'Inter',sans-serif;transition:all 0.2s;}
.sub-cat-link:hover{border-color:var(--border-glow);box-shadow:var(--neon-glow);}
</style>
<div class="cat-page-hero">
  <div style="display:inline-block;background:var(--tag-bg);color:var(--neon);border:1px solid var(--border);padding:0.3rem 0.9rem;border-radius:20px;font-size:0.8rem;font-weight:600;letter-spacing:1px;text-transform:uppercase;margin-bottom:1rem;font-family:'Inter',sans-serif;">Category</div>
  <h1>⚡ <span>Research</span></h1>
  <p>Articles and guides about Research.</p>
</div>

<div class="grid2" id="posts-grid"><div style="grid-column:1/-1;text-align:center;padding:40px;color:var(--muted);font-size:12px;">Loading articles...</div></div>
<script>
var ALL_POSTS=[{% for post in site.posts %}{"title":{{ post.title | jsonify }},"url":{{ post.url | jsonify }},"date":{{ post.date | date: "%Y-%m-%d" | jsonify }},"category":{{ post.categories | first | jsonify }},"image":{{ post.image | default: "" | jsonify }}}{% unless forloop.last %},{% endunless %}{% endfor %}];
var CAT="Research";
var grid=document.getElementById('posts-grid');
var posts=ALL_POSTS.filter(function(p){return p.category===CAT;});
if(posts.length===0){grid.innerHTML='<div style="grid-column:1/-1;text-align:center;padding:40px;color:var(--muted);">No articles yet in this category.</div>';}
else{var html='';posts.forEach(function(p){html+='<a class="gcard" href="'+p.url+'"><div class="gc-img">'+(p.image?'<img src="'+p.image+'" alt="'+p.title+'" loading="lazy"/>':'<span style="font-size:32px;opacity:0.2;">⚡</span>')+'</div><div class="gc-body"><span class="ctag">'+p.category+'</span><h3>'+p.title+'</h3><div class="cmeta"><span>'+p.date+'</span><span class="cread">Read →</span></div></div></a>';});grid.innerHTML=html;}
</script>
