---
layout: default
title: "Contact ARYXGuide"
description: "Get in touch with ARYXGuide. Questions about AI tools, health and beauty, or study content — or anything else. The inbox is open."
permalink: /contact-us/
sitemap: true
---

<style>
.contact-wrap { max-width: 720px; margin: 0 auto; padding: 32px 0 60px; }
.contact-intro {
  background: var(--bg-card); border: 1px solid var(--border);
  border-radius: var(--radius-lg); padding: 32px; margin-bottom: 20px;
}
.contact-intro-title {
  font-family: var(--font-head); font-size: clamp(24px, 3.5vw, 34px);
  font-weight: 700; color: var(--text); margin-bottom: 16px; letter-spacing: -0.3px;
}
.contact-intro p {
  font-size: 15.5px; line-height: 1.85; color: var(--text-2); margin-bottom: 14px;
}
.contact-intro p:last-child { margin-bottom: 0; }

.contact-reasons {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 10px; margin-top: 20px;
}
.reason-item {
  display: flex; align-items: flex-start; gap: 10px;
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-sm); padding: 12px 14px;
  font-size: 13px; color: var(--text-2); line-height: 1.5;
}
.reason-dot {
  width: 6px; height: 6px; border-radius: 50%;
  flex-shrink: 0; margin-top: 6px;
}
.reason-dot.ai { background: var(--ai-primary); }
.reason-dot.hb { background: var(--hb-primary); }
.reason-dot.st { background: var(--st-primary); }

.form-card {
  background: var(--bg-card); border: 1px solid var(--border);
  border-radius: var(--radius-lg); padding: 32px;
}
.form-card-title {
  font-family: var(--font-head); font-size: 18px; font-weight: 700;
  color: var(--text); margin-bottom: 24px;
}
.form-group {
  display: flex; flex-direction: column; margin-bottom: 18px;
}
.form-group label {
  font-size: 11px; font-weight: 700; letter-spacing: 1px;
  text-transform: uppercase; color: var(--text-3); margin-bottom: 8px;
}
.form-group input,
.form-group textarea,
.form-group select {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-sm);
  padding: 12px 16px;
  font-size: 14px; color: var(--text);
  font-family: var(--font-body);
  outline: none;
  transition: border-color 0.2s;
  appearance: none;
}
.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus {
  border-color: var(--ai-primary);
  background: var(--bg-card);
}
.form-group input::placeholder,
.form-group textarea::placeholder { color: var(--text-3); }
.form-group textarea { min-height: 150px; resize: vertical; line-height: 1.6; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.form-submit {
  width: 100%;
  background: var(--ai-primary);
  color: #fff; border: none;
  border-radius: var(--radius-sm);
  padding: 14px;
  font-size: 13px; font-weight: 700;
  letter-spacing: 1px; text-transform: uppercase;
  cursor: pointer;
  transition: opacity 0.2s, transform 0.15s;
  font-family: var(--font-body);
  margin-top: 4px;
}
.form-submit:hover { opacity: 0.88; transform: translateY(-1px); }
.form-submit:active { transform: translateY(0); }
.form-submit:disabled { opacity: 0.5; cursor: not-allowed; transform: none; }
.form-success {
  display: none; margin-top: 16px;
  background: rgba(34,197,94,0.1); border: 1px solid rgba(34,197,94,0.25);
  border-radius: var(--radius-sm); padding: 14px;
  text-align: center; color: #22c55e; font-size: 14px; font-weight: 600;
}
.form-error {
  display: none; margin-top: 16px;
  background: rgba(239,68,68,0.1); border: 1px solid rgba(239,68,68,0.25);
  border-radius: var(--radius-sm); padding: 14px;
  text-align: center; color: #ef4444; font-size: 14px; font-weight: 600;
}
.response-note {
  font-size: 12px; color: var(--text-3);
  text-align: center; margin-top: 14px; line-height: 1.6;
}
@media (max-width: 560px) {
  .form-row { grid-template-columns: 1fr; }
  .contact-reasons { grid-template-columns: 1fr; }
  .contact-intro, .form-card { padding: 22px 18px; }
}
</style>

<div class="contact-wrap">

  <div class="contact-intro">
    <h1 class="contact-intro-title">Get in Touch</h1>
    <p>The inbox is open. If you found something useful here, spotted something wrong, or have a question about any of the content on this site, a message gets a real reply, usually within 24 hours.</p>
    <p>For business inquiries, collaboration ideas, or anything that needs a longer back-and-forth, email works better than a quick form submission. Mention what it is about in the subject line and it will get handled faster.</p>

    <div class="contact-reasons">
      <div class="reason-item"><div class="reason-dot ai"></div>Questions about AI tools, SEO, or blogging content</div>
      <div class="reason-item"><div class="reason-dot hb"></div>Health and beauty article feedback or corrections</div>
      <div class="reason-item"><div class="reason-dot st"></div>Study and career guide questions or suggestions</div>
      <div class="reason-item"><div class="reason-dot ai"></div>Corrections to outdated or inaccurate information</div>
      <div class="reason-item"><div class="reason-dot hb"></div>Collaboration or partnership inquiries</div>
      <div class="reason-item"><div class="reason-dot st"></div>Content requests or topic suggestions</div>
    </div>
  </div>

  <div class="form-card">
    <div class="form-card-title">Send a Message</div>
    <form id="contact-form" novalidate>
      <div class="form-row">
        <div class="form-group">
          <label for="cf-name">Your Name</label>
          <input type="text" id="cf-name" name="name" placeholder="Aryx K." required />
        </div>
        <div class="form-group">
          <label for="cf-email">Email Address</label>
          <input type="email" id="cf-email" name="email" placeholder="you@example.com" required />
        </div>
      </div>
      <div class="form-group">
        <label for="cf-topic">Topic</label>
        <select id="cf-topic" name="topic">
          <option value="">Select a topic</option>
          <option value="AI Guide">AI Guide question</option>
          <option value="Health & Beauty">Health & Beauty question</option>
          <option value="Study & Career">Study & Career question</option>
          <option value="Correction">Article correction</option>
          <option value="Collaboration">Collaboration or partnership</option>
          <option value="Other">Something else</option>
        </select>
      </div>
      <div class="form-group">
        <label for="cf-message">Message</label>
        <textarea id="cf-message" name="message" placeholder="What would you like to say?" required></textarea>
      </div>
      <button class="form-submit" type="submit" id="cf-btn">Send Message</button>
      <div class="form-success" id="cf-success">Message sent. You will hear back within 24 hours.</div>
      <div class="form-error" id="cf-error">Something went wrong. Please try again.</div>
      <p class="response-note">Typical response time is within 24 hours. For urgent matters, mention it in your message.</p>
    </form>
  </div>

</div>

<script>
document.getElementById('contact-form').addEventListener('submit', function(e) {
  e.preventDefault();
  var btn   = document.getElementById('cf-btn');
  var succ  = document.getElementById('cf-success');
  var err   = document.getElementById('cf-error');
  succ.style.display = 'none';
  err.style.display  = 'none';
  btn.textContent = 'Sending...';
  btn.disabled = true;
  fetch('https://formspree.io/f/maqpbvgy', {
    method: 'POST',
    body: new FormData(this),
    headers: { 'Accept': 'application/json' }
  }).then(function(res) {
    if (res.ok) {
      succ.style.display = 'block';
      document.getElementById('contact-form').reset();
    } else {
      err.style.display = 'block';
    }
    btn.textContent = 'Send Message';
    btn.disabled = false;
  }).catch(function() {
    err.style.display = 'block';
    btn.textContent = 'Send Message';
    btn.disabled = false;
  });
});
</script>
