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
