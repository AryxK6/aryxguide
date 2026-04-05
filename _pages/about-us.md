---
layout: default
title: "About Us"
permalink: /about-us
---

<style>
.aryx-about-wrap {
  font-family: 'Segoe UI', system-ui, sans-serif;
  width: 100%;
  box-sizing: border-box;
  color: #e2e8f0;
}
.aryx-about-wrap .ab-card {
  background: #0f0f1a;
  border: 1px solid #1e1e3a;
  border-radius: 14px;
  padding: 28px 24px;
  margin-bottom: 18px;
}
.aryx-about-wrap .ab-title {
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #4f8ef7;
  margin: 0 0 18px 0;
  padding-bottom: 12px;
  border-bottom: 1px solid #1e1e3a;
  display: flex;
  align-items: center;
  gap: 8px;
}
.aryx-about-wrap .ab-title::before {
  content: '';
  width: 3px;
  height: 14px;
  background: linear-gradient(180deg, #4f8ef7, #8b5cf6);
  border-radius: 2px;
  display: inline-block;
  flex-shrink: 0;
}
.aryx-about-wrap p {
  font-size: 14px;
  line-height: 1.8;
  color: #94a3b8;
  margin: 0 0 14px 0;
}
.aryx-about-wrap p:last-child {
  margin-bottom: 0;
}
.aryx-about-wrap .ab-highlight {
  color: #e2e8f0;
  font-weight: 500;
}
.aryx-about-wrap .ab-topics {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  margin-top: 4px;
}
.aryx-about-wrap .ab-topic-item {
  background: #13131f;
  border: 1px solid #1e1e3a;
  border-radius: 8px;
  padding: 10px 14px;
  font-size: 12px;
  color: #94a3b8;
  display: flex;
  align-items: center;
  gap: 8px;
}
.aryx-about-wrap .ab-topic-item::before {
  content: '';
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: linear-gradient(135deg, #4f8ef7, #8b5cf6);
  flex-shrink: 0;
}
.aryx-about-wrap .ab-author {
  display: flex;
  align-items: flex-start;
  gap: 16px;
}
.aryx-about-wrap .ab-author-avatar {
  width: 52px;
  height: 52px;
  border-radius: 50%;
  flex-shrink: 0;
  overflow: hidden;
  border: 2px solid #4f8ef7;
}
.aryx-about-wrap .ab-author-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.aryx-about-wrap .ab-author-info {
  flex: 1;
}
.aryx-about-wrap .ab-author-name {
  font-size: 15px;
  font-weight: 700;
  color: #e2e8f0;
  margin-bottom: 4px;
}
.aryx-about-wrap .ab-author-role {
  font-size: 11px;
  color: #4f8ef7;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 10px;
}
.aryx-about-wrap .ab-author-bio {
  font-size: 13px;
  line-height: 1.75;
  color: #94a3b8;
  margin: 0;
}
.aryx-about-wrap .ab-contact-row {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 12px 14px;
  background: #13131f;
  border: 1px solid #1e1e3a;
  border-radius: 8px;
  text-decoration: none;
  transition: border-color 0.2s;
  margin-top: 14px;
}
.aryx-about-wrap .ab-contact-row:hover {
  border-color: #4f8ef7;
}
.aryx-about-wrap .ab-contact-icon {
  font-size: 16px;
}
.aryx-about-wrap .ab-contact-text {
  font-size: 13px;
  color: #94a3b8;
}
.aryx-about-wrap .ab-contact-text span {
  color: #4f8ef7;
  font-weight: 600;
}
</style>

<div class="aryx-about-wrap">

  <!-- About the Blog -->
  <div class="ab-card">
    <div class="ab-title">About ARYX</div>
    <p>Most tech content online does one of two things it either assumes you already know everything, or it buries the actual answer under ten paragraphs of fluff. ARYX is my attempt to fix that.</p>
    <p>This blog covers AI tools, blogging, SEO, and online income. Not the theory. The stuff I actually use, test, and build with. What works, what doesn't, and the honest reasons why.</p>
    <p class="ab-highlight">No filler. No vague "experts say" claims. Just real information you can act on.</p>
  </div>

  <!-- What We Cover -->
  <div class="ab-card">
    <div class="ab-title">What We Cover</div>
    <div class="ab-topics">
      <div class="ab-topic-item">AI Tools &amp; Reviews</div>
      <div class="ab-topic-item">SEO &amp; Blogging</div>
      <div class="ab-topic-item">Online Income</div>
      <div class="ab-topic-item">Content Creation</div>
      <div class="ab-topic-item">Productivity</div>
      <div class="ab-topic-item">AI Tutorials</div>
    </div>
  </div>

  <!-- Author -->
  <div class="ab-card">
    <div class="ab-title">The Person Behind It</div>
    <div class="ab-author">
      <div class="ab-author-avatar"><img src="https://i.supaimg.com/e2d7b027-0330-470f-ab98-2277696b7201/d3cbb013-4192-4974-8134-c0bcc7ecc3ea.png" alt="Aryx K." /></div>
      <div class="ab-author-info">
        <div class="ab-author-name">Aryx K.</div>
        <div class="ab-author-role">Blogger &amp; Content Creator</div>
        <p class="ab-author-bio">I've been building online for a while writing, testing content strategies, and figuring out how to make AI tools actually useful rather than just impressive-sounding. ARYX documents what I've learned. If something here helped you, that's the whole point.</p>
      </div>
    </div>
    <a href="https://www.aryxguide.site/p/contact-us.html" class="ab-contact-row">
      <span class="ab-contact-icon">✉</span>
      <span class="ab-contact-text">Have a question? <span>Get in touch →</span></span>
    </a>
  </div>

</div>

