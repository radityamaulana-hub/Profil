<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Portofolio pribadi Rhaditya Maulana, mahasiswa Politeknik Indonusa." />
  <title>Rhaditya Maulana — Personal Portfolio</title>
  <style>
    :root {
      --bg: #f7f8fa;
      --surface: #ffffff;
      --text: #17191d;
      --muted: #707783;
      --line: #e7e9ed;
      --accent: #315efb;
      --accent-soft: #edf1ff;
      --radius: 22px;
      --shadow: 0 18px 50px rgba(24, 34, 58, .07);
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: var(--bg); color: var(--text); line-height: 1.65;
    }
    a { color: inherit; text-decoration: none; }
    .container { width: min(1080px, calc(100% - 40px)); margin: auto; }
    .navbar {
      position: sticky; top: 0; z-index: 10; background: rgba(247,248,250,.88);
      backdrop-filter: blur(14px); border-bottom: 1px solid rgba(231,233,237,.8);
    }
    .nav-inner { height: 76px; display: flex; align-items: center; justify-content: space-between; }
    .brand { font-size: 1.05rem; font-weight: 800; letter-spacing: -.04em; }
    .brand span { color: var(--accent); }
    .nav-links { display: flex; gap: 30px; align-items: center; color: var(--muted); font-size: .9rem; }
    .nav-links a:hover { color: var(--accent); }
    .menu-btn { display: none; border: 0; background: none; font-size: 1.5rem; cursor: pointer; }
    .hero { padding: 92px 0 78px; display: grid; grid-template-columns: 1.35fr .65fr; gap: 60px; align-items: center; }
    .eyebrow { display: inline-flex; align-items: center; gap: 9px; color: var(--accent); font-size: .78rem; font-weight: 750; letter-spacing: .12em; text-transform: uppercase; }
    .eyebrow::before { content: ""; width: 24px; height: 1px; background: var(--accent); }
    h1 { margin: 18px 0 18px; font-size: clamp(2.8rem, 7vw, 5.3rem); line-height: 1.04; letter-spacing: -.075em; font-weight: 800; }
    h1 span { color: var(--accent); }
    .hero-copy { max-width: 570px; color: var(--muted); font-size: 1.06rem; }
    .actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 30px; }
    .btn { display: inline-flex; align-items: center; justify-content: center; padding: 12px 19px; border-radius: 999px; font-size: .9rem; font-weight: 700; transition: .2s ease; }
    .btn-primary { background: var(--text); color: white; }
    .btn-primary:hover { background: var(--accent); transform: translateY(-2px); }
    .btn-outline { border: 1px solid var(--line); background: white; }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); }
    .profile-card { background: var(--surface); border: 1px solid var(--line); border-radius: 28px; padding: 16px; box-shadow: var(--shadow); transform: rotate(2deg); }
    .profile-art { min-height: 310px; border-radius: 19px; background: linear-gradient(145deg, #e9edff, #f5f6fb 60%, #dce5ff); display: grid; place-items: center; position: relative; overflow: hidden; }
    .profile-art::before, .profile-art::after { content: ""; position: absolute; border: 1px solid rgba(49,94,251,.16); border-radius: 50%; width: 230px; height: 230px; }
    .profile-art::after { width: 300px; height: 300px; }
    .initials { width: 142px; height: 142px; display: grid; place-items: center; border-radius: 50%; background: white; color: var(--accent); font-size: 2.7rem; font-weight: 800; letter-spacing: -.08em; box-shadow: 0 12px 35px rgba(49,94,251,.15); z-index: 1; }
    .card-caption { padding: 17px 8px 5px; display: flex; justify-content: space-between; align-items: center; gap: 10px; }
    .card-caption strong { display: block; font-size: .95rem; }
    .card-caption small { color: var(--muted); }
    .status { width: 9px; height: 9px; background: #36b37e; border-radius: 50%; display: inline-block; margin-right: 6px; }
    section { padding: 65px 0; }
    .section-head { display: flex; align-items: end; justify-content: space-between; gap: 20px; margin-bottom: 28px; }
    .section-kicker { color: var(--accent); font-size: .76rem; font-weight: 800; text-transform: uppercase; letter-spacing: .13em; }
    h2 { font-size: clamp(1.8rem, 4vw, 2.6rem); letter-spacing: -.055em; line-height: 1.15; margin-top: 8px; }
    .section-note { max-width: 360px; color: var(--muted); font-size: .92rem; }
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 18px; }
    .panel { background: var(--surface); border: 1px solid var(--line); border-radius: var(--radius); padding: 28px; }
    .panel p { color: var(--muted); }
    .facts { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
    .fact small { color: var(--muted); display: block; margin-bottom: 4px; }
    .fact strong { font-size: .98rem; }
    .skills { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
    .skill { background: white; border: 1px solid var(--line); border-radius: var(--radius); padding: 25px; transition: .2s ease; }
    .skill:hover { transform: translateY(-5px); box-shadow: var(--shadow); border-color: #d7defe; }
    .skill-number { color: var(--accent); font-size: .78rem; font-weight: 800; }
    .skill h3 { margin: 17px 0 7px; font-size: 1.08rem; letter-spacing: -.02em; }
    .skill p { color: var(--muted); font-size: .9rem; }
    .tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 17px; }
    .tag { background: var(--accent-soft); color: #3454c7; border-radius: 999px; padding: 5px 10px; font-size: .75rem; font-weight: 700; }
    .contact { background: #17191d; color: white; border-radius: 28px; padding: 42px; display: flex; align-items: center; justify-content: space-between; gap: 25px; }
    .contact p { color: #aeb4bf; margin-top: 10px; max-width: 480px; }
    .contact .btn { background: white; color: #17191d; white-space: nowrap; }
    footer { padding: 28px 0 38px; color: var(--muted); font-size: .83rem; display: flex; justify-content: space-between; gap: 15px; }
    .reveal { opacity: 0; transform: translateY(18px); transition: opacity .65s ease, transform .65s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }
    @media (max-width: 760px) {
      .nav-links { display: none; position: absolute; top: 76px; left: 0; right: 0; padding: 18px 22px 22px; background: var(--bg); border-bottom: 1px solid var(--line); flex-direction: column; align-items: flex-start; gap: 16px; }
      .nav-links.open { display: flex; }
      .menu-btn { display: block; }
      .hero { padding: 65px 0 48px; grid-template-columns: 1fr; gap: 38px; }
      .profile-card { max-width: 390px; width: 100%; margin: auto; }
      .profile-art { min-height: 250px; }
      section { padding: 48px 0; }
      .section-head { display: block; }
      .section-note { margin-top: 12px; }
      .about-grid, .skills { grid-template-columns: 1fr; }
      .contact { padding: 30px; align-items: flex-start; flex-direction: column; }
      footer { flex-direction: column; }
    }
    @media (prefers-reduced-motion: reduce) { html { scroll-behavior: auto; } *, *::before, *::after { transition-duration: .01ms !important; animation-duration: .01ms !important; } }
  </style>
</head>
<body>
  <nav class="navbar">
    <div class="container nav-inner">
      <a class="brand" href="#home">R<span>.</span>M</a>
      <button class="menu-btn" id="menuBtn" aria-label="Buka menu" aria-expanded="false">☰</button>
      <div class="nav-links" id="navLinks">
        <a href="#home">Beranda</a><a href="#about">Tentang</a><a href="#skills">Keahlian</a><a href="#contact">Kontak</a>
      </div>
    </div>
  </nav>

  <main>
    <header class="container hero" id="home">
      <div>
        <div class="eyebrow">Personal Portfolio</div>
        <h1>Halo, saya<br><span>Rhaditya Maulana.</span></h1>
        <p class="hero-copy">Mahasiswa Politeknik Indonusa yang tertarik pada dunia teknologi dan pengembangan web. Saya senang membangun website yang sederhana, fungsional, dan memiliki tampilan menarik.</p>
        <div class="actions">
          <a class="btn btn-primary" href="#skills">Lihat Keahlian <span aria-hidden="true">↗</span></a>
          <a class="btn btn-outline" href="#contact">Hubungi Saya</a>
        </div>
      </div>
      <div class="profile-card" aria-label="Kartu profil Rhaditya Maulana">
        <div class="profile-art"><div class="initials">RM</div></div>
        <div class="card-caption">
          <div><strong>Rhaditya Maulana</strong><small>Mahasiswa · Politeknik Indonusa</small></div>
          <span title="Terus belajar"><span class="status"></span><small>Learning</small></span>
        </div>
      </div>
    </header>

    <section id="about">
      <div class="container">
        <div class="section-head reveal">
          <div><div class="section-kicker">01 — Tentang Saya</div><h2>Mengenal saya lebih dekat.</h2></div>
          <p class="section-note">Terus belajar, mencoba hal baru, dan mengembangkan kemampuan di bidang teknologi.</p>
        </div>
        <div class="about-grid reveal">
          <article class="panel"><p>Saya Rhaditya Maulana, mahasiswa di Politeknik Indonusa. Saya memiliki ketertarikan pada pembuatan website dan ingin terus mengembangkan kemampuan di bidang teknologi informasi. Bagi saya, setiap proyek adalah kesempatan untuk belajar dan menghasilkan sesuatu yang bermanfaat.</p></article>
          <article class="panel facts">
            <div class="fact"><small>Nama</small><strong>Rhaditya Maulana</strong></div>
            <div class="fact"><small>Status</small><strong>Mahasiswa</strong></div>
            <div class="fact"><small>Kampus</small><strong>Politeknik Indonusa</strong></div>
            <div class="fact"><small>Minat</small><strong>Web Development</strong></div>
          </article>
        </div>
      </div>
    </section>

    <section id="skills">
      <div class="container">
        <div class="section-head reveal">
          <div><div class="section-kicker">02 — Keahlian</div><h2>Hal yang sedang saya kembangkan.</h2></div>
          <p class="section-note">Beberapa kemampuan yang saya pelajari dan terus tingkatkan.</p>
        </div>
        <div class="skills">
          <article class="skill reveal"><span class="skill-number">01 / WEB</span><h3>Pembuatan Website</h3><p>Membuat halaman website yang terstruktur, responsif, dan mudah digunakan.</p><div class="tags"><span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">JavaScript</span></div></article>
          <article class="skill reveal"><span class="skill-number">02 / DESIGN</span><h3>Desain Tampilan</h3><p>Menyusun tata letak dan tampilan antarmuka yang bersih serta nyaman dilihat.</p><div class="tags"><span class="tag">Layout</span><span class="tag">Responsive</span></div></article>
          <article class="skill reveal"><span class="skill-number">03 / GROWTH</span><h3>Belajar Teknologi</h3><p>Mempelajari tools dan teknologi baru untuk meningkatkan kemampuan membuat proyek digital.</p><div class="tags"><span class="tag">Problem Solving</span><span class="tag">Learning</span></div></article>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="contact reveal">
          <div><div class="section-kicker" style="color:#aabaff">03 — Kontak</div><h2>Mari terhubung.</h2><p>Terima kasih sudah mengunjungi profil saya. Silakan hubungi saya untuk berdiskusi, berbagi ide, atau berkolaborasi.</p></div>
          <!-- Ganti alamat email di bawah dengan email aktif milik Anda. -->
          <a class="btn" href="mailto:emailkamu@example.com">Kirim Email ↗</a>
        </div>
      </div>
    </section>
  </main>

  <footer class="container"><span>© <span id="year"></span> Rhaditya Maulana</span><span>Dibuat dengan HTML, CSS & JavaScript.</span></footer>

  <script>
    // Menu navigasi untuk tampilan mobile
    const menuBtn = document.getElementById('menuBtn');
    const navLinks = document.getElementById('navLinks');
    menuBtn.addEventListener('click', () => {
      const isOpen = navLinks.classList.toggle('open');
      menuBtn.setAttribute('aria-expanded', isOpen);
      menuBtn.textContent = isOpen ? '×' : '☰';
    });
    navLinks.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        navLinks.classList.remove('open');
        menuBtn.setAttribute('aria-expanded', 'false');
        menuBtn.textContent = '☰';
      });
    });

    // Tahun footer otomatis mengikuti tahun saat ini
    document.getElementById('year').textContent = new Date().getFullYear();

    // Animasi elemen saat masuk ke area layar
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.12 });
    document.querySelectorAll('.reveal').forEach(element => observer.observe(element));
  </script>
</body>
</html>

