---
layout: default
title: "About ARYXGuide — Digital Guide, Health & Beauty, Study, Personal Finance"
description: "ARYXGuide covers AI tools, health and beauty, study and career, and personal finance. Written by Aryx K., who has been building content sites since 2026."
permalink: /about-us/
sitemap: true
---

<style>
.about-wrap { max-width: 860px; margin: 0 auto; padding: 32px 0 60px; }
.ab-section {
  background: var(--bg-card); border: 1px solid var(--border);
  border-radius: var(--radius-lg); padding: 32px; margin-bottom: 20px;
}
.ab-label {
  font-size: 9px; font-weight: 700; letter-spacing: 2.5px;
  text-transform: uppercase; color: var(--text-3);
  margin-bottom: 20px; padding-bottom: 14px;
  border-bottom: 1px solid var(--divider);
  display: flex; align-items: center; gap: 10px;
}
.ab-label::before {
  content: ''; width: 3px; height: 14px;
  background: linear-gradient(180deg, var(--ai-primary), var(--hb-primary));
  border-radius: 2px; flex-shrink: 0;
}
.ab-h1 {
  font-family: var(--font-head);
  font-size: clamp(26px, 4vw, 38px); font-weight: 700;
  color: var(--text); margin-bottom: 20px;
  line-height: 1.2; letter-spacing: -0.4px;
}
.ab-p {
  font-size: 15.5px; line-height: 1.85;
  color: var(--text-2); margin-bottom: 16px;
}
.ab-p:last-child { margin-bottom: 0; }
.ab-p strong { color: var(--text); font-weight: 600; }
.ab-h2 {
  font-family: var(--font-head); font-size: 18px; font-weight: 700;
  color: var(--text); margin: 22px 0 10px;
}
.ab-stats {
  display: grid; grid-template-columns: repeat(4, 1fr);
  gap: 12px; margin: 24px 0 4px;
}
.ab-stat {
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-md); padding: 18px; text-align: center;
}
.ab-stat-num {
  font-family: var(--font-head); font-size: 28px; font-weight: 700;
  display: block; line-height: 1; margin-bottom: 6px;
}
.ab-stat-num.ai { color: var(--ai-primary); }
.ab-stat-num.hb { color: var(--hb-primary); }
.ab-stat-num.st { color: var(--st-primary); }
.ab-stat-num.pf { color: var(--pf-primary); }
.ab-stat-label { font-size: 11px; color: var(--text-3); font-weight: 600; }
.niches-grid {
  display: grid; grid-template-columns: repeat(2, 1fr);
  gap: 14px; margin-top: 20px;
}
.niche-card {
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-md); padding: 20px;
  transition: border-color 0.2s, transform 0.2s;
}
.niche-card:hover { transform: translateY(-2px); }
.niche-card.ai:hover { border-color: var(--ai-border); }
.niche-card.hb:hover { border-color: var(--hb-border); }
.niche-card.st:hover { border-color: var(--st-border); }
.niche-card.pf:hover { border-color: var(--pf-border); }
.niche-card-marker {
  width: 10px; height: 10px; border-radius: 50%;
  margin-bottom: 12px; display: block;
}
.ai .niche-card-marker { background: var(--ai-primary); box-shadow: 0 0 6px var(--ai-primary); }
.hb .niche-card-marker { background: var(--hb-primary); }
.st .niche-card-marker { background: var(--st-primary); }
.pf .niche-card-marker { background: var(--pf-primary); }
.niche-card-title {
  font-family: var(--font-head); font-size: 15px; font-weight: 700;
  margin-bottom: 10px;
}
.niche-card.ai .niche-card-title { color: var(--ai-primary); }
.niche-card.hb .niche-card-title { color: var(--hb-primary); }
.niche-card.st .niche-card-title { color: var(--st-primary); }
.niche-card.pf .niche-card-title { color: var(--pf-primary); }
.niche-card-topics { font-size: 12.5px; color: var(--text-2); line-height: 1.65; }
.author-block { display: flex; align-items: flex-start; gap: 20px; }
.author-avatar-lg {
  width: 72px; height: 72px; border-radius: 50%;
  overflow: hidden; flex-shrink: 0;
  border: 2px solid var(--border-strong); background: var(--ai-dim);
}
.author-avatar-lg img { width: 100%; height: 100%; object-fit: cover; display: block; }
.author-info-name {
  font-family: var(--font-head); font-size: 20px; font-weight: 700;
  color: var(--text); margin-bottom: 4px;
}
.author-info-role {
  font-size: 11px; font-weight: 700; letter-spacing: 1px;
  text-transform: uppercase; color: var(--ai-primary); margin-bottom: 12px;
}
.author-info-bio { font-size: 14px; line-height: 1.8; color: var(--text-2); }
.work-grid {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 10px; margin-top: 16px;
}
.work-item {
  display: flex; align-items: flex-start; gap: 10px;
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-sm); padding: 12px 14px;
  font-size: 13px; color: var(--text-2); line-height: 1.5;
}
.work-dot {
  width: 6px; height: 6px; border-radius: 50%;
  background: var(--ai-primary); flex-shrink: 0; margin-top: 6px;
}
.contact-cta {
  display: flex; align-items: center; gap: 12px;
  padding: 14px 18px;
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-md);
  text-decoration: none; transition: border-color 0.2s; margin-top: 20px;
}
.contact-cta:hover { border-color: var(--ai-primary); }
.contact-cta-text { font-size: 14px; color: var(--text-2); }
.contact-cta-text span { color: var(--ai-primary); font-weight: 700; }
.niche-pill-row { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 20px; }
@media (max-width: 700px) {
  .niches-grid { grid-template-columns: 1fr; }
  .ab-stats { grid-template-columns: repeat(2, 1fr); }
  .work-grid { grid-template-columns: 1fr; }
  .author-block { flex-direction: column; }
}
@media (max-width: 480px) {
  .ab-section { padding: 22px 18px; }
}
</style>

<div class="about-wrap">

  <div class="ab-section">
    <div class="niche-pill-row">
      <span class="niche-pill pill-ai">Digital Guide</span>
      <span class="niche-pill pill-hb">Health & Beauty</span>
      <span class="niche-pill pill-st">Study</span>
      <span class="niche-pill pill-pf">Personal Finance</span>
    </div>
    <h1 class="ab-h1">About ARYXGuide</h1>
    <p class="ab-p">Most content online makes the same two mistakes. It assumes you already understand what you are doing, or it buries the answer under paragraphs that say nothing useful. ARYXGuide is an attempt to fix that across four areas where this problem shows up constantly: digital tools and AI, health and beauty, study and career development, and personal finance.</p>
    <p class="ab-p">Each section works the same way. Research what people actually need to know. Test where possible. Write it straight, with enough detail to be useful, without the padding that makes most online guides frustrating to read.</p>
    <p class="ab-p"><strong>ARYXGuide launched in 2026.</strong> What started as a single-topic blog has expanded into a proper multi-subject publication. The approach has stayed the same throughout.</p>

    <div class="ab-stats">
      <div class="ab-stat">
        <span class="ab-stat-num ai">80+</span>
        <div class="ab-stat-label">Articles</div>
      </div>
      <div class="ab-stat">
        <span class="ab-stat-num hb">4</span>
        <div class="ab-stat-label">Niches</div>
      </div>
      <div class="ab-stat">
        <span class="ab-stat-num st">2026</span>
        <div class="ab-stat-label">Building Since</div>
      </div>
      <div class="ab-stat">
        <span class="ab-stat-num pf">Free</span>
        <div class="ab-stat-label">Always</div>
      </div>
    </div>
  </div>

  <div class="ab-section">
    <div class="ab-label">What This Site Covers</div>
    <p class="ab-p">ARYXGuide covers four areas. Each has its own section and category structure, so you can go straight to what you need.</p>

    <div class="niches-grid">
      <div class="niche-card ai">
        <span class="niche-card-marker"></span>
        <div class="niche-card-title">Digital Guide</div>
        <div class="niche-card-topics">AI tools, tutorials, image and video generation, voice AI, SEO, blogging, content writing, affiliate marketing, digital products, passive income, freelancing, eCommerce, social media, email marketing, YouTube, productivity, and automation.</div>
      </div>
      <div class="niche-card hb">
        <span class="niche-card-marker"></span>
        <div class="niche-card-title">Health & Beauty</div>
        <div class="niche-card-topics">Skin care routines, anti-aging, acne treatment, hair care and growth, body care, makeup, health and wellness, mental health, nutrition, sleep, gut health, women's health, natural DIY beauty, and honest product reviews without influencer bias.</div>
      </div>
      <div class="niche-card st">
        <span class="niche-card-marker"></span>
        <div class="niche-card-title">Study & Career</div>
        <div class="niche-card-topics">Study tips and productivity systems, career guidance, resume and interview help, certifications, online courses, freelancing and remote work, personal growth, digital skills, college life, and communication skills for students and early-career professionals.</div>
      </div>
      <div class="niche-card pf">
        <span class="niche-card-marker"></span>
        <div class="niche-card-title">Personal Finance</div>
        <div class="niche-card-topics">Money basics and financial literacy, budgeting and planning, saving strategies, student finance, online income, investing basics, wealth building, money mindset, and practical tools for managing money on a real income.</div>
      </div>
    </div>

    <p class="ab-p" style="margin-top:20px;">Every article gets researched or tested before it goes up. If something is based on personal experience, that is stated. If something cited as fact has a source, the source is either linked or named. Articles get updated when information changes rather than left live with outdated content misleading people.</p>
  </div>

  <div class="ab-section">
    <div class="ab-label">The Person Behind It</div>
    <div class="author-block">
      <div class="author-avatar-lg">
        <img src="https://i.ibb.co/1YWBXwxG/ARYX.png" alt="Aryx K." onerror="this.style.display='none'"/>
      </div>
      <div>
        <div class="author-info-name">Aryx K.</div>
        <div class="author-info-role">Blogger & Content Creator</div>
        <div class="author-info-bio">Building content sites since 2026. Started with SEO and monetization on a single blog, then moved into AI tools as they became too useful to ignore. Over time, the site expanded into health content, career guidance, and personal finance because the same problems existed in all of them: generic advice, outdated information, and articles written to rank rather than to help. ARYXGuide is where that gets fixed.</div>
      </div>
    </div>

    <h2 class="ab-h2">Background</h2>
    <div class="work-grid">
      <div class="work-item"><div class="work-dot"></div><div>Built and monetized content sites in the AI, blogging, and online business space from scratch with no existing audience or budget.</div></div>
      <div class="work-item"><div class="work-dot"></div><div>Tested over 30 AI writing, design, image generation, and automation tools across real tasks, not just demo scenarios.</div></div>
      <div class="work-item"><div class="work-dot"></div><div>Researched and written health and beauty content with focus on ingredient evidence and honest product assessments without sponsored bias.</div></div>
      <div class="work-item"><div class="work-dot"></div><div>Covered career and study topics including certifications, freelancing platforms, and job search strategies based on current market conditions.</div></div>
      <div class="work-item"><div class="work-dot"></div><div>Written personal finance content for people who are not starting from a position of financial comfort, covering budgeting, saving, and building income on a real-world income.</div></div>
      <div class="work-item"><div class="work-dot"></div><div>Worked with Google Search Console, AdSense, and on-page SEO for new blogs with no backlink profile.</div></div>
    </div>

    <a href="/contact-us/" class="contact-cta">
      <div class="contact-cta-text">Questions or want to get in touch? <span>Send a message →</span></div>
    </a>
  </div>

  <div class="ab-section">
    <div class="ab-label">How This Site Operates</div>
    <p class="ab-p">The same approach applies across all four sections. Research or test before writing. Say clearly when something is personal experience versus cited information. Update content when it becomes outdated rather than leaving it live as-is.</p>
    <p class="ab-p">ARYXGuide uses affiliate links and display advertising to cover operating costs. That is explained in full on the <a href="/affiliate-disclosure/" style="color:var(--ai-primary);">Affiliate Disclosure</a> page. The short version: affiliate relationships follow editorial judgment, not the other way around. A product gets recommended because it is worth recommending. The affiliate program follows from that, not before it.</p>
    <p class="ab-p">If something on this site is wrong, outdated, or unclear, the <a href="/contact-us/" style="color:var(--ai-primary);">contact form</a> is there. It gets checked and responded to.</p>
  </div>

</div>
