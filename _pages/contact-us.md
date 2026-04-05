---
layout: default
title: "Contact Us"
permalink: /contact-us
---

<style>
.aryx-contact-page {
  max-width: 720px;
  margin: 0 auto;
  padding: 0 0 40px 0;
  font-family: inherit;
}
.aryx-contact-page .ac-intro {
  margin-bottom: 32px;
}
.aryx-contact-page .ac-intro p {
  font-size: 15px;
  line-height: 1.8;
  margin: 0 0 12px 0;
  opacity: 0.85;
}
.aryx-contact-page .ac-email {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(79, 142, 247, 0.08);
  border: 1px solid rgba(79, 142, 247, 0.2);
  border-radius: 8px;
  padding: 10px 16px;
  font-size: 14px;
  font-weight: 600;
  color: #4f8ef7;
  margin-top: 4px;
  text-decoration: none;
}
.aryx-form-wrap {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 14px;
  padding: 28px 28px 24px;
}
.aryx-form-wrap .af-title {
  font-size: 17px;
  font-weight: 700;
  margin-bottom: 22px;
  letter-spacing: 0.3px;
}
.aryx-form-wrap .af-group {
  display: flex;
  flex-direction: column;
  margin-bottom: 16px;
}
.aryx-form-wrap .af-group label {
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 0.6px;
  text-transform: uppercase;
  opacity: 0.6;
  margin-bottom: 7px;
}
.aryx-form-wrap .af-group input,
.aryx-form-wrap .af-group textarea {
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 8px;
  padding: 11px 14px;
  font-size: 14px;
  color: inherit;
  font-family: inherit;
  outline: none;
  transition: border 0.2s;
}
.aryx-form-wrap .af-group input:focus,
.aryx-form-wrap .af-group textarea:focus {
  border-color: #4f8ef7;
}
.aryx-form-wrap .af-group textarea {
  min-height: 130px;
  resize: vertical;
}
.aryx-form-wrap .af-btn {
  width: 100%;
  background: linear-gradient(135deg, #4f8ef7, #8b5cf6);
  color: #fff;
  border: none;
  border-radius: 8px;
  padding: 13px;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 1px;
  text-transform: uppercase;
  cursor: pointer;
  transition: opacity 0.2s, transform 0.15s;
  margin-top: 4px;
}
.aryx-form-wrap .af-btn:hover {
  opacity: 0.9;
  transform: translateY(-1px);
}
.aryx-form-wrap .af-btn:active {
  transform: translateY(0);
}
.aryx-form-wrap .af-success {
  display: none;
  background: rgba(79, 247, 141, 0.08);
  border: 1px solid rgba(79, 247, 141, 0.2);
  border-radius: 8px;
  padding: 14px;
  text-align: center;
  color: #4ff78d;
  font-size: 13px;
  font-weight: 600;
  margin-top: 14px;
}
.aryx-form-wrap .af-error {
  display: none;
  background: rgba(247, 79, 79, 0.08);
  border: 1px solid rgba(247, 79, 79, 0.2);
  border-radius: 8px;
  padding: 14px;
  text-align: center;
  color: #f74f4f;
  font-size: 13px;
  font-weight: 600;
  margin-top: 14px;
}
</style>

<div class="aryx-contact-page">

  <div class="ac-intro">
    <p>Got a question, found something useful here, or just want to say hi the inbox is open. Response time is usually within 24 hours, sometimes less.</p>
    <p>For business inquiries, collaborations, or anything that needs a real back-and-forth, email works best.</p>
  </div>

  <div class="aryx-form-wrap">
    <div class="af-title">Send a Message</div>
    <form id="aryx-contact-form">
      <div class="af-group">
        <label>Your Name</label>
        <input name="name" required="" type="text" />
      </div>
      <div class="af-group">
        <label>Email Address</label>
        <input name="email" required="" type="email" />
      </div>
      <div class="af-group">
        <label>Subject</label>
        <input name="subject" placeholder="What is this about?" type="text" />
      </div>
      <div class="af-group">
        <label>Message</label>
        <textarea name="message" required=""></textarea>
      </div>
      <button class="af-btn" type="submit">Send Message</button>
      <div class="af-success" id="af-success">✓ Message sent! We'll get back to you soon.</div>
      <div class="af-error" id="af-error">Something went wrong. Please try again.</div>
    </form>
  </div>

</div>

<script>
document.getElementById('aryx-contact-form').addEventListener('submit', function(e) {
  e.preventDefault();
  var btn = this.querySelector('.af-btn');
  var success = document.getElementById('af-success');
  var error = document.getElementById('af-error');
  btn.textContent = 'Sending...';
  btn.disabled = true;
  success.style.display = 'none';
  error.style.display = 'none';
  var data = new FormData(this);
  fetch('https://formspree.io/f/maqpbvgy', {
    method: 'POST',
    body: data,
    headers: { 'Accept': 'application/json' }
  }).then(function(res) {
    if (res.ok) {
      success.style.display = 'block';
      document.getElementById('aryx-contact-form').reset();
    } else {
      error.style.display = 'block';
    }
    btn.textContent = 'Send Message';
    btn.disabled = false;
  }).catch(function() {
    error.style.display = 'block';
    btn.textContent = 'Send Message';
    btn.disabled = false;
  });
});
</script>

