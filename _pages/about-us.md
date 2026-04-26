---
layout: default
title: "About ARYXGuide — AI Tools, Health & Beauty, Study Guides"
description: "ARYXGuide covers AI tools, health and beauty, and study and career guides. Written and tested by Aryx K., who has been building content sites since 2022."
permalink: /about-us/
sitemap: true
---

<style>
.about-wrap { max-width: 860px; margin: 0 auto; padding: 32px 0 60px; }
.ab-section {
  background: var(--bg-card);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 32px;
  margin-bottom: 20px;
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
.ab-h2 {
  font-family: var(--font-head);
  font-size: 18px; font-weight: 700;
  color: var(--text); margin: 22px 0 10px;
}
.ab-p {
  font-size: 15.5px; line-height: 1.85;
  color: var(--text-2); margin-bottom: 16px;
}
.ab-p:last-child { margin-bottom: 0; }
.ab-p strong { color: var(--text); font-weight: 600; }

.ab-stats {
  display: grid; grid-template-columns: repeat(3, 1fr);
  gap: 12px; margin: 24px 0 4px;
}
.ab-stat {
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-md); padding: 18px; text-align: center;
}
.ab-stat-num {
  font-family: var(--font-head); font-size: 30px; font-weight: 700;
  display: block; line-height: 1; margin-bottom: 6px;
}
.ab-stat-num.ai { color: var(--ai-primary); }
.ab-stat-num.hb { color: var(--hb-primary); }
.ab-stat-num.st { color: var(--st-primary); }
.ab-stat-label { font-size: 11px; color: var(--text-3); font-weight: 600; }

.niches-grid {
  display: grid; grid-template-columns: repeat(3, 1fr);
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
.niche-card-icon { font-size: 24px; margin-bottom: 10px; }
.niche-card-title {
  font-family: var(--font-head); font-size: 15px; font-weight: 700;
  margin-bottom: 10px;
}
.niche-card.ai .niche-card-title { color: var(--ai-primary); }
.niche-card.hb .niche-card-title { color: var(--hb-primary); }
.niche-card.st .niche-card-title { color: var(--st-primary); }
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

.what-we-test {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 10px; margin-top: 16px;
}
.test-item {
  display: flex; align-items: flex-start; gap: 10px;
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-sm); padding: 12px 14px;
  font-size: 13px; color: var(--text-2); line-height: 1.5;
}
.test-item::before {
  content: ''; width: 6px; height: 6px; border-radius: 50%;
  background: var(--ai-primary); flex-shrink: 0; margin-top: 6px;
}

.contact-row {
  display: flex; align-items: center; gap: 12px;
  padding: 14px 18px;
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-md);
  text-decoration: none; transition: border-color 0.2s; margin-top: 20px;
}
.contact-row:hover { border-color: var(--ai-primary); }
.contact-row-icon { font-size: 18px; }
.contact-row-text { font-size: 14px; color: var(--text-2); }
.contact-row-text span { color: var(--ai-primary); font-weight: 700; }

.niche-pill-row { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 20px; }

@media (max-width: 700px) {
  .niches-grid { grid-template-columns: 1fr; }
  .ab-stats { grid-template-columns: repeat(3, 1fr); }
  .what-we-test { grid-template-columns: 1fr; }
  .author-block { flex-direction: column; }
}
@media (max-width: 480px) {
  .ab-stats { grid-template-columns: 1fr; }
  .ab-section { padding: 22px 18px; }
}
</style>

<div class="about-wrap">

  <!-- Intro -->
  <div class="ab-section">
    <div class="niche-pill-row">
      <span class="niche-pill pill-ai">⚡ AI Guide</span>
      <span class="niche-pill pill-hb">🌸 Health & Beauty</span>
      <span class="niche-pill pill-st">📚 Study</span>
    </div>
    <h1 class="ab-h1">About ARYXGuide</h1>
    <p class="ab-p">Most content online does one of two things. It assumes you already know what you are doing, or it buries the actual answer under paragraphs that say nothing. ARYXGuide is my attempt to fix that across three areas I genuinely spend time in: AI tools, health and beauty, and study and career development.</p>
    <p class="ab-p">Each section works the same way. I look at what people actually want to know, test it where I can, and write it straight. No "experts suggest" without something to back it up. No lists padded out to hit a word count. Just the information, explained clearly, with enough detail to be useful.</p>
    <p class="ab-p"><strong>The site has grown a lot since 2022.</strong> What started as an AI and blogging blog has expanded into a proper multi-topic resource. The standards have stayed the same throughout.</p>

    <div class="ab-stats">
      <div class="ab-stat">
        <span class="ab-stat-num ai">50+</span>
        <div class="ab-stat-label">Articles Published</div>
      </div>
      <div class="ab-stat">
        <span class="ab-stat-num hb">3</span>
        <div class="ab-stat-label">Content Niches</div>
      </div>
      <div class="ab-stat">
        <span class="ab-stat-num st">2022</span>
        <div class="ab-stat-label">Building Online Since</div>
      </div>
    </div>
  </div>

  <!-- What This Site Covers -->
  <div class="ab-section">
    <div class="ab-label">What We Cover</div>
    <p class="ab-p">ARYXGuide covers three areas. Each one has its own section with its own category structure, so you can go straight to what you need without sifting through unrelated content.</p>

    <div class="niches-grid">
      <div class="niche-card ai">
        <div class="niche-card-icon">⚡</div>
        <div class="niche-card-title">AI Guide</div>
        <div class="niche-card-topics">AI tools and reviews, tutorials, image and video generation, voice AI, coding, affiliate marketing, digital products, passive income, freelancing, SEO, blogging, social media, email marketing, YouTube, productivity, and automation.</div>
      </div>
      <div class="niche-card hb">
        <div class="niche-card-icon">🌸</div>
        <div class="niche-card-title">Health & Beauty</div>
        <div class="niche-card-topics">Skin care routines and ingredients, hair care and growth, body care, makeup tips, health and wellness, nutrition, mental health, women's health, natural and DIY beauty, and honest product reviews without the influencer bias.</div>
      </div>
      <div class="niche-card st">
        <div class="niche-card-icon">📚</div>
        <div class="niche-card-title">Study & Career</div>
        <div class="niche-card-topics">Study tips and productivity systems, career guidance, resume and interview help, online courses and certifications, freelancing and remote work, personal growth, digital skills, college life, and tools that actually make a difference.</div>
      </div>
    </div>

    <p class="ab-p" style="margin-top:20px;">Every article on this site gets researched or tested before it goes up. If I have not used something personally, I say so and explain what I based the piece on instead. If something that used to work has stopped working the way older guides describe, I update it rather than leave it there misleading people.</p>
  </div>

  <!-- Author -->
  <div class="ab-section">
    <div class="ab-label">The Person Behind It</div>
    <div class="author-block">
      <div class="author-avatar-lg">
        <img
          src="https://i.ibb.co/1YWBXwxG/ARYX.png"
          alt="Aryx K., creator of ARYXGuide"
          onerror="this.style.display='none'"
        />
      </div>
      <div>
        <div class="author-info-name">Aryx K.</div>
        <div class="author-info-role">Blogger & Content Creator</div>
        <div class="author-info-bio">I have been building content sites since 2022. Started with figuring out SEO and AdSense on a single blog, then moved into testing AI tools as they became impossible to ignore. Over time, that expanded into health content and career guidance because those are areas I was reading and learning about anyway, and the same problems existed there: generic advice, outdated information, and articles written to rank rather than to help. ARYXGuide is where I document what I actually find useful.</div>
      </div>
    </div>

    <h2 class="ab-h2">What I have worked on</h2>
    <div class="what-we-test">
      <div class="test-item">Built and monetized content sites in the AI, blogging, and make-money-online space from scratch with no existing audience.</div>
      <div class="test-item">Tested over 30 AI writing, design, image generation, and automation tools across real use cases, not just demos.</div>
      <div class="test-item">Researched and written health and beauty content with a focus on ingredient evidence and honest product assessments.</div>
      <div class="test-item">Covered career and study topics including certifications, freelancing platforms, and job search strategies that work in the current market.</div>
      <div class="test-item">Worked with Google Search Console, AdSense approval processes, and on-page SEO for newer blogs with no backlink profile.</div>
      <div class="test-item">Expanded a single-niche site into a structured multi-niche publication while keeping the content quality consistent across all three areas.</div>
    </div>

    <a href="/contact-us/" class="contact-row">
      <span class="contact-row-icon">✉️</span>
      <span class="contact-row-text">Have a question or want to get in touch? <span>Send a message →</span></span>
    </a>
  </div>

  <!-- Editorial Standards -->
  <div class="ab-section">
    <div class="ab-label">How We Write</div>
    <p class="ab-p">The same approach applies across all three niches. Research or test before writing. State clearly when something is personal experience versus cited information. Avoid hedging claims with vague phrases like "experts suggest" when no specific expert is being cited. Update content when it becomes outdated rather than leaving it live as-is.</p>
    <p class="ab-p">ARYXGuide does use affiliate links and display advertising to cover the cost of running the site. That is explained fully on the <a href="/affiliate-disclosure/" style="color:var(--ai-primary);">Affiliate Disclosure</a> page. The short version: affiliate relationships follow editorial judgment, not the other way around. A product does not get a positive write-up because it has an affiliate program. If it is genuinely useful, that comes first and the affiliate link follows. If it is not, it does not get recommended regardless of whether a commission is available.</p>
    <p class="ab-p">If something on this site is wrong, outdated, or unclear, the <a href="/contact-us/" style="color:var(--ai-primary);">contact form</a> is there. I would rather know about it than have incorrect information sitting here for months.</p>
  </div>

</div>
