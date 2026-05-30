<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Metalwork & Creative Portfolio — Student</title>
<meta name="description" content="Portfolio for a Metalwork Technology and Education student who loves photography, music and creativity." />
<style>
  :root{
    --bg:#0f1724;
    --card:#0b1220;
    --accent:#ff6b6b;
    --muted:#9aa4b2;
    --glass: rgba(255,255,255,0.04);
    --radius:14px;
    --max-width:1100px;
    --gap:20px;
    --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, "Roboto Mono", "Segoe UI Mono", monospace;
    --sans: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  }

  /* Reset & base */
  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0;
    font-family:var(--sans);
    background:
      radial-gradient(1200px 600px at 10% 10%, rgba(255,107,107,0.06), transparent 6%),
      linear-gradient(180deg,#071021 0%, var(--bg) 100%);
    color:#e6eef6;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    line-height:1.45;
    padding:32px;
    display:flex;
    justify-content:center;
  }

  .wrap{
    width:100%;
    max-width:var(--max-width);
    margin:0 auto;
    display:grid;
    grid-template-columns: 1fr;
    gap:var(--gap);
  }

  header{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:16px;
  }

  .brand{
    display:flex;
    gap:12px;
    align-items:center;
  }

  .logo{
    width:64px;
    height:64px;
    border-radius:12px;
    background:linear-gradient(135deg,var(--accent),#ffd166);
    display:flex;
    align-items:center;
    justify-content:center;
    color:#08101a;
    font-weight:700;
    font-family:var(--mono);
    box-shadow:0 6px 18px rgba(0,0,0,0.45);
  }

  nav a{
    color:var(--muted);
    text-decoration:none;
    margin-left:18px;
    font-weight:600;
    font-size:0.95rem;
  }
  nav a:hover, nav a:focus{color:#fff; outline:none; text-decoration:underline}

  /* Hero */
  .hero{
    background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
    padding:28px;
    border-radius:var(--radius);
    display:grid;
    grid-template-columns: 1fr 360px;
    gap:24px;
    align-items:center;
    box-shadow: 0 8px 30px rgba(2,6,23,0.6);
  }

  .intro h1{
    margin:0 0 8px 0;
    font-size:clamp(1.6rem, 2.6vw, 2.4rem);
    letter-spacing:-0.02em;
  }
  .intro p{margin:0 0 16px 0; color:var(--muted)}
  .cta{
    display:flex;
    gap:12px;
    margin-top:12px;
  }
  .btn{
    background:var(--accent);
    color:#08101a;
    padding:10px 14px;
    border-radius:10px;
    font-weight:700;
    border:none;
    cursor:pointer;
    box-shadow:0 6px 18px rgba(255,107,107,0.12);
  }
  .btn.secondary{
    background:transparent;
    color:var(--muted);
    border:1px solid rgba(255,255,255,0.04);
    font-weight:600;
  }

  /* Profile card */
  .profile{
    background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
    padding:18px;
    border-radius:12px;
    display:flex;
    gap:12px;
    align-items:center;
    justify-content:flex-start;
  }
  .avatar{
    width:84px;
    height:84px;
    border-radius:12px;
    background:
      linear-gradient(135deg,#ffd166,#ff6b6b);
    display:flex;
    align-items:center;
    justify-content:center;
    color:#08101a;
    font-weight:800;
    font-family:var(--mono);
    font-size:1.1rem;
  }
  .meta small{color:var(--muted); display:block}
  .tags{margin-top:8px; display:flex; gap:8px; flex-wrap:wrap}
  .tag{background:var(--glass); padding:6px 8px; border-radius:8px; color:var(--muted); font-weight:600; font-size:0.85rem}

  /* Sections */
  section{
    background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent);
    padding:20px;
    border-radius:12px;
  }

  .grid-2{
    display:grid;
    grid-template-columns: 1fr 360px;
    gap:20px;
  }

  .skills{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
  }
  .skill{
    background:linear-gradient(90deg, rgba(255,255,255,0.02), transparent);
    padding:10px 12px;
    border-radius:10px;
    color:var(--muted);
    font-weight:700;
    font-size:0.9rem;
  }

  /* Projects / gallery */
  .projects-grid{
    display:grid;
    grid-template-columns: repeat(auto-fit, minmax(220px,1fr));
    gap:14px;
  }
  .card{
    background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
    border-radius:12px;
    overflow:hidden;
    box-shadow:0 8px 24px rgba(2,6,23,0.45);
    transition:transform .28s ease, box-shadow .28s ease;
  }
  .card:hover{transform:translateY(-6px); box-shadow:0 18px 40px rgba(2,6,23,0.6)}
  .card img{width:100%; height:160px; object-fit:cover; display:block}
  .card .card-body{padding:12px}
  .card h4{margin:0 0 6px 0}
  .card p{margin:0; color:var(--muted); font-size:0.95rem}

  /* Gallery thumbnails */
  .thumbs{display:grid; grid-template-columns: repeat(3,1fr); gap:8px}
  .thumbs img{width:100%; height:110px; object-fit:cover; border-radius:8px; cursor:pointer; display:block}

  /* Lightbox modal */
  .lightbox{
    position:fixed; inset:0; display:none; align-items:center; justify-content:center;
    background:rgba(2,6,23,0.8); z-index:1200; padding:24px;
  }
  .lightbox.open{display:flex}
  .lightbox img{max-width:90%; max-height:80%; border-radius:10px; box-shadow:0 18px 60px rgba(0,0,0,0.7)}

  /* Music */
  .playlist{display:flex; flex-direction:column; gap:10px}
  .track{
    display:flex; align-items:center; gap:12px; padding:8px; border-radius:10px; background:var(--glass);
  }
  .track strong{display:block}
  audio{width:100%; outline:none}

  /* Contact */
  .contact-form{display:grid; gap:10px}
  .contact-form input, .contact-form textarea{
    background:transparent; border:1px solid rgba(255,255,255,0.06); padding:10px; border-radius:8px; color:inherit;
  }
  .contact-form button{justify-self:start}

  /* Footer */
  footer{display:flex; justify-content:space-between; align-items:center; gap:12px; color:var(--muted); font-size:0.9rem}

  /* Responsive */
  @media (max-width:980px){
    .hero, .grid-2{grid-template-columns:1fr}
    .profile{justify-content:space-between}
    .thumbs{grid-template-columns: repeat(2,1fr)}
  }
  @media (max-width:520px){
    body{padding:18px}
    .thumbs img{height:90px}
  }

  /* Focus */
  a:focus, button:focus, input:focus, textarea:focus{outline:3px solid rgba(255,107,107,0.18); outline-offset:3px}
</style>
</head>
<body>
  <div class="wrap" role="main">
    <header>
      <div class="brand">
        <div class="logo" aria-hidden="true">MT</div>
        <div>
          <div style="font-weight:800">David — Metalwork Student</div>
          <div style="color:var(--muted);font-size:0.9rem">Metalwork Technology & Education • Photography • Music</div>
        </div>
      </div>
      <nav aria-label="Primary">
        <a href="#about">About</a>
        <a href="#projects">Projects</a>
        <a href="#gallery">Photography</a>
        <a href="#music">Music</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <section class="hero" aria-labelledby="hero-title">
      <div class="intro">
        <h1 id="hero-title">Crafting metal, capturing light, composing sound.</h1>
        <p>I'm a Metalwork Technology and Education student blending hands-on fabrication with visual storytelling and music. I teach, make, and create — from welded sculptures to photo series and original tracks.</p>
        <div class="cta">
          <a class="btn" href="#projects">View Projects</a>
          <a class="btn secondary" href="#contact">Get in touch</a>
        </div>

        <div style="margin-top:18px; display:flex; gap:12px; flex-wrap:wrap">
          <div class="skill">Metal Fabrication</div>
          <div class="skill">Teaching & Curriculum</div>
          <div class="skill">Photography</div>
          <div class="skill">Music Production</div>
        </div>
      </div>

      <aside class="profile" aria-label="Profile card">
        <div class="avatar" aria-hidden="true">D</div>
        <div class="meta">
          <div style="font-weight:800">David</div>
          <small>Metalwork Technology & Education student</small>
          <div class="tags" aria-hidden="true">
            <span class="tag">Welding</span>
            <span class="tag">CNC</span>
            <span class="tag">Portraits</span>
            <span class="tag">Indie/Electronic</span>
          </div>
        </div>
      </aside>
    </section>

    <section id="about" aria-labelledby="about-title">
      <h3 id="about-title">About</h3>
      <div class="grid-2" style="align-items:start">
        <div>
          <p>I combine technical metalwork skills with creative practice and classroom experience. My work explores material, texture, and light — whether I'm teaching a workshop, fabricating a lamp, or shooting a portrait series.</p>
          <p><strong>Interests:</strong> sustainable fabrication, educational design, documentary photography, modular synths, and collaborative projects.</p>
        </div>
        <div>
          <h4>Quick facts</h4>
          <ul style="color:var(--muted); margin:8px 0 0 18px">
            <li>Currently studying Metalwork Technology & Education</li>
            <li>Experience with MIG/TIG welding, sheet metal, and CNC</li>
            <li>Exhibitions: student shows and local galleries</li>
          </ul>
        </div>
      </div>
    </section>

    <section id="projects" aria-labelledby="projects-title">
      <h3 id="projects-title">Projects</h3>
      <div class="projects-grid" style="margin-top:12px">
        <article class="card" aria-labelledby="p1">
          <img src="https://images.unsplash.com/photo-1549880338-65ddcdfd017b?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="Welded lamp project">
          <div class="card-body">
            <h4 id="p1">Welded Lamp Series</h4>
            <p>Hand-fabricated desk lamps exploring negative space and warm diffusion. Taught a workshop on safe TIG basics.</p>
          </div>
        </article>

        <article class="card" aria-labelledby="p2">
          <img src="https://images.unsplash.com/photo-1515879218367-8466d910aaa4?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="CNC metalwork">
          <div class="card-body">
            <h4 id="p2">CNC Educational Kit</h4>
            <p>Designed a modular metal kit for classroom demonstrations of machining and joinery.</p>
          </div>
        </article>

        <article class="card" aria-labelledby="p3">
          <img src="https://images.unsplash.com/photo-1504198453319-5ce911bafcde?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="Photo series">
          <div class="card-body">
            <h4 id="p3">Portrait Series: Makers</h4>
            <p>Documentary portraits of local makers, printed in a zine and shown at the student gallery.</p>
          </div>
        </article>
      </div>
    </section>

    <section id="gallery" aria-labelledby="gallery-title">
      <h3 id="gallery-title">Photography</h3>
      <p style="color:var(--muted)">Click a thumbnail to view larger.</p>
      <div class="thumbs" style="margin-top:12px">
        <img src="https://images.unsplash.com/photo-1504198453319-5ce911bafcde?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="Portrait 1" data-full="https://images.unsplash.com/photo-1504198453319-5ce911bafcde?q=80&w=1600&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder">
        <img src="https://images.unsplash.com/photo-1515879218367-8466d910aaa4?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="Workshop" data-full="https://images.unsplash.com/photo-1515879218367-8466d910aaa4?q=80&w=1600&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder">
        <img src="https://images.unsplash.com/photo-1549880338-65ddcdfd017b?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="Metal detail" data-full="https://images.unsplash.com/photo-1549880338-65ddcdfd017b?q=80&w=1600&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder">
      </div>
    </section>

    <section id="music" aria-labelledby="music-title">
      <h3 id="music-title">Music</h3>
      <p style="color:var(--muted)">A selection of original tracks and sketches. Use the player to listen.</p>
      <div class="playlist" style="margin-top:12px">
        <div class="track">
          <div style="width:48px;height:48px;border-radius:8px;background:linear-gradient(135deg,#ffd166,#ff6b6b);display:flex;align-items:center;justify-content:center;font-weight:800;color:#08101a">01</div>
          <div style="flex:1">
            <strong>Foundry Nights</strong>
            <div style="color:var(--muted);font-size:0.9rem">Ambient textures with metallic percussion</div>
          </div>
          <audio controls preload="none" src="https://cdn.simplecast.com/audio/placeholder.mp3"></audio>
        </div>

        <div class="track">
          <div style="width:48px;height:48px;border-radius:8px;background:linear-gradient(135deg,#6be7ff,#6b6bff);display:flex;align-items:center;justify-content:center;font-weight:800;color:#08101a">02</div>
          <div style="flex:1">
            <strong>Workshop Waltz</strong>
            <div style="color:var(--muted);font-size:0.9rem">Rhythmic loops inspired by shop tools</div>
          </div>
          <audio controls preload="none" src="https://cdn.simplecast.com/audio/placeholder2.mp3"></audio>
        </div>
      </div>
    </section>

    <section id="contact" aria-labelledby="contact-title">
      <h3 id="contact-title">Contact</h3>
      <div style="display:grid; grid-template-columns: 1fr 320px; gap:18px; align-items:start">
        <form class="contact-form" onsubmit="event.preventDefault(); alert('Message sent (demo).');" aria-label="Contact form">
          <input type="text" name="name" placeholder="Your name" required />
          <input type="email" name="email" placeholder="Your email" required />
          <input type="text" name="subject" placeholder="Subject" />
          <textarea name="message" rows="5" placeholder="Message" required></textarea>
          <button class="btn" type="submit">Send message</button>
        </form>

        <aside style="color:var(--muted)">
          <h4>Availability</h4>
          <p>Open to collaborations, teaching assistant roles, and commissions. Based in Kaduna State, Nigeria.</p>
          <h4 style="margin-top:12px">Quick links</h4>
          <ul style="margin:8px 0 0 18px; color:var(--muted)">
            <li><a href="#" style="color:var(--muted)">Resume (PDF)</a></li>
            <li><a href="#" style="color:var(--muted)">Instagram / Photo</a></li>
            <li><a href="#" style="color:var(--muted)">SoundCloud / Tracks</a></li>
          </ul>
        </aside>
      </div>
    </section>

    <footer>
      <div>© <strong>David</strong> — Metalwork Technology & Education</div>
      <div style="color:var(--muted)">Built with HTML & CSS • Designed for creativity</div>
    </footer>
  </div>

  <!-- Lightbox modal (minimal JS) -->
  <div id="lightbox" class="lightbox" role="dialog" aria-modal="true" aria-hidden="true">
    <img id="lightbox-img" alt="Expanded photo">
  </div>

<script>
  // Simple gallery lightbox
  (function(){
    const thumbs = document.querySelectorAll('.thumbs img');
    const lightbox = document.getElementById('lightbox');
    const lbImg = document.getElementById('lightbox-img');

    thumbs.forEach(t => {
      t.addEventListener('click', () => {
        const src = t.dataset.full || t.src;
        lbImg.src = src;
        lightbox.classList.add('open');
        lightbox.setAttribute('aria-hidden','false');
      });
    });

    lightbox.addEventListener('click', (e) => {
      if (e.target === lightbox || e.target === lbImg) {
        lightbox.classList.remove('open');
        lightbox.setAttribute('aria-hidden','true');
        lbImg.src = '';
      }
    });

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') {
        lightbox.classList.remove('open');
        lightbox.setAttribute('aria-hidden','true');
        lbImg.src = '';
      }
    });
  })();
</script>
</body>
</html>g
