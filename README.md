[script.js](https://github.com/user-attachments/files/22986536/script.js)

// Smooth scroll
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener('click', e => {
    const href = a.getAttribute('href');
    if(href.length > 1){
      e.preventDefault();
      document.querySelector(href).scrollIntoView({behavior:'smooth'});
    }
  });
});

// Simple form handler using mailto or fetch to formspree (user can replace)
const form = document.getElementById('contact-form');
if(form){
  form.addEventListener('submit', (e) => {
    e.preventDefault();
    const data = new FormData(form);
    const name = data.get('name');
    const email = data.get('email');
    const phone = data.get('phone');
    const message = data.get('message');
    const subject = encodeURIComponent('Painters Vision Inquiry');
    const body = encodeURIComponent(`Name: ${name}\nEmail: ${email}\nPhone: ${phone}\n\n${message}`);
    window.location.href = `mailto:info@paintersvision.com?subject=${subject}&body=${body}`;
  });
}

:root {
  --blue: #12143A;
  --purple: #44186E;
  --lime: #83DC48;
  --text: #F5F7FB;
  --muted: #B7B9C6;
  --card: #1E205A;
  --card2: #30206E;
}
* { box-sizing: border-box; }
html, body { margin:0; padding:0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji"; color: var(--text); background: linear-gradient(180deg,var(--blue),var(--purple)); }
a { color: var(--lime); text-decoration: none; }
a:hover { text-decoration: underline; }
.container { width: min(1200px, 92vw); margin: 0 auto; }
.nav { position: sticky; top:0; background: rgba(18,20,58,.8); backdrop-filter: blur(8px); z-index: 20; border-bottom: 1px solid rgba(255,255,255,.08); }
.nav-inner { display:flex; align-items:center; justify-content: space-between; padding: 14px 0; }
.nav .brand { display:flex; align-items:center; gap:12px; }
.logo { width: 46px; height: 46px; object-fit: contain; }
.btn { display:inline-block; padding: 12px 18px; border-radius: 999px; background: var(--lime); color:#0B0D1B; font-weight:700; border: 0; cursor: pointer; }
.btn-outline { background: transparent; color: var(--text); border: 2px solid var(--lime); }
.btn:hover { filter: brightness(1.05); }
.hero { padding: 72px 0 32px; }
.hero-inner { display:grid; grid-template-columns: 1.1fr .9fr; gap: 28px; align-items:center; }
@media (max-width: 900px) { .hero-inner { grid-template-columns: 1fr; } }
.badge { display:inline-flex; align-items:center; gap:10px; padding: 8px 14px; border-radius: 999px; background: rgba(131,220,72,.15); color: var(--lime); border: 1px solid rgba(131,220,72,.35); letter-spacing: .3px; }
.h1 { font-size: clamp(36px, 4vw, 52px); line-height:1.1; margin: 14px 0; }
.p { color: var(--muted); font-size: 18px; }
.hero-card { background: linear-gradient(180deg,var(--card), var(--card2)); border-radius: 18px; padding: 22px; border: 1px solid rgba(255,255,255,.08); }
.grid-3 { display:grid; grid-template-columns: repeat(3,1fr); gap:18px; }
@media (max-width: 1000px) { .grid-3 { grid-template-columns: 1fr; } }
.section { padding: 56px 0; }
.section h2 { font-size: 34px; margin: 0 0 14px; }
.card { background: linear-gradient(180deg,var(--card), var(--card2)); border-radius: 18px; padding: 20px; border: 1px solid rgba(255,255,255,.08); }
.card h3 { margin-top:0; }
.price { font-size: 38px; font-weight: 800; color: var(--lime); }
.list { margin: 12px 0 0 0; padding:0; list-style:none; }
.list li { margin: 10px 0; display:flex; gap:10px; align-items:flex-start; }
.list li::before { content: "✔"; color: var(--lime); margin-top: 2px; }
.table { width:100%; border-collapse: collapse; }
.table th, .table td { padding: 12px; border-bottom: 1px solid rgba(255,255,255,.08); text-align: left; }
.table th { color: var(--lime); }
.cta { text-align:center; padding: 40px 0; }
.badge-note { font-size: 12px; color: var(--muted); }
.footer { border-top: 1px solid rgba(255,255,255,.08); padding: 24px 0 52px; color: var(--muted); }
.kpis { display:grid; grid-template-columns: repeat(4,1fr); gap: 18px; }
.kpis .kpi { text-align:center; background: rgba(255,255,255,.05); border: 1px solid rgba(255,255,255,.08); padding: 16px; border-radius: 12px; }
@media (max-width: 900px) { .kpis { grid-template-columns: repeat(2,1fr); } }
input, textarea, select { width:100%; padding: 12px 14px; border-radius: 12px; border: 1px solid rgba(255,255,255,.15); background: rgba(10,12,32,.6); color: var(--text); }
.form-row { display:grid; grid-template-columns: 1fr 1fr; gap: 16px; }
@media (max-width: 900px) { .form-row { grid-template-columns: 1fr; } }
label { font-size: 14px; color: var(--muted); margin-bottom: 6px; display:block; }
.small { font-size: 14px; color: var(--muted); }
.hero-cta { display:flex; gap: 14px; flex-wrap: wrap; align-items:center; }
.shadow-xl { box-shadow: 0 20px 60px rgba(0,0,0,.35); }
