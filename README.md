<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="Nonchopper Official Portfolio — Web、ビジュアル、ブランド制作のポートフォリオ">
  <meta name="theme-color" content="#090909">
  <title>Nonchopper — Official Portfolio</title>
  <style>
    :root {
      --bg: #090909;
      --panel: #121212;
      --fg: #f5f5f5;
      --muted: #a4a4a4;
      --subtle: #707070;
      --border: rgba(255, 255, 255, 0.14);
      --accent: #d7b56d;
      --font-main: -apple-system, BlinkMacSystemFont, "Helvetica Neue", Arial, sans-serif;
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; scroll-padding-top: 24px; }
    body { background: var(--bg); color: var(--fg); font-family: var(--font-main); line-height: 1.7; }
    a { color: var(--fg); text-decoration: none; }
    a:hover { color: var(--accent); }
    :focus-visible { outline: 2px solid var(--accent); outline-offset: 4px; }

    .page { max-width: 1200px; margin: 0 auto; padding: 40px 24px 80px; }

    header { display: flex; justify-content: space-between; align-items: center; gap: 24px; border-bottom: 1px solid var(--border); padding-bottom: 16px; margin-bottom: 72px; }
    .logo { color: var(--fg); font-size: 14px; letter-spacing: 0.2em; text-transform: uppercase; white-space: nowrap; }
    nav ul { display: flex; flex-wrap: wrap; gap: 12px 24px; list-style: none; }
    nav a { position: relative; color: var(--muted); font-size: 12px; letter-spacing: 0.16em; text-transform: uppercase; transition: color 0.25s ease; }
    nav a::after { position: absolute; right: 0; bottom: -6px; left: 0; height: 1px; background: var(--accent); content: ""; transform: scaleX(0); transform-origin: right; transition: transform 0.25s ease; }
    nav a:hover::after, nav a:focus-visible::after { transform: scaleX(1); transform-origin: left; }

    .hero { display: grid; grid-template-columns: minmax(0, 1.1fr) minmax(280px, 0.9fr); gap: clamp(32px, 6vw, 80px); align-items: center; margin-bottom: 96px; }
    .eyebrow { margin-bottom: 20px; color: var(--accent); font-size: 11px; letter-spacing: 0.2em; text-transform: uppercase; }
    .hero-title { max-width: 700px; font-size: clamp(2.25rem, 6vw, 5.5rem); font-weight: 500; letter-spacing: 0.08em; line-height: 1.05; text-transform: uppercase; }
    .hero-sub { max-width: 520px; margin-top: 24px; color: var(--muted); font-size: 15px; }
    .hero-meta { display: flex; flex-wrap: wrap; gap: 10px 20px; margin-top: 32px; color: var(--subtle); font-size: 11px; letter-spacing: 0.16em; text-transform: uppercase; }
    .hero-actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 36px; }
    .button { display: inline-block; border: 1px solid var(--border); padding: 11px 18px; color: var(--fg); font-size: 11px; letter-spacing: 0.14em; text-transform: uppercase; transition: border-color 0.25s ease, background 0.25s ease, color 0.25s ease; }
    .button:hover, .button:focus-visible { border-color: var(--accent); background: var(--accent); color: #111; }
    .button--quiet { border-color: transparent; color: var(--muted); }

    .hero-image { position: relative; aspect-ratio: 4 / 5; overflow: hidden; border: 1px solid var(--border); padding: 18px; background: var(--panel); }
    .hero-image-inner { width: 100%; height: 100%; background: radial-gradient(circle at 68% 24%, rgba(215, 181, 109, 0.45), transparent 25%), linear-gradient(145deg, #252525 0%, #0c0c0c 55%, #34302a 100%); }
    .hero-image-inner::after { display: block; width: 100%; height: 100%; background: linear-gradient(120deg, transparent 20%, rgba(255, 255, 255, 0.08), transparent 65%); content: ""; }
    .hero-caption { position: absolute; bottom: 30px; left: 30px; color: #ddd; font-size: 10px; letter-spacing: 0.16em; text-transform: uppercase; }

    section { margin-bottom: 96px; }
    .section-header { display: flex; justify-content: space-between; align-items: baseline; gap: 20px; margin-bottom: 28px; border-top: 1px solid var(--border); padding-top: 16px; }
    .section-title { font-size: 13px; font-weight: 500; letter-spacing: 0.18em; text-transform: uppercase; }
    .section-sub { color: var(--subtle); font-size: 12px; }

    .gallery-grid { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 18px; }
    .gallery-item { position: relative; aspect-ratio: 4 / 5; overflow: hidden; border: 1px solid var(--border); background: var(--panel); }
    .gallery-thumb { position: absolute; inset: 0; background-size: cover; background-position: center; opacity: 0.9; transition: transform 0.4s ease, opacity 0.4s ease; }
    .gallery-item:nth-child(1) .gallery-thumb { background: linear-gradient(145deg, #4a4032, #121212 60%); }
    .gallery-item:nth-child(2) .gallery-thumb { background: linear-gradient(35deg, #262626, #776d5b 48%, #101010 49%); }
    .gallery-item:nth-child(3) .gallery-thumb { background: radial-gradient(circle at 35% 30%, #777 0 3%, transparent 4%), linear-gradient(145deg, #161616, #413b33); }
    .gallery-item:hover .gallery-thumb, .gallery-item:focus-within .gallery-thumb { transform: scale(1.04); opacity: 1; }
    .gallery-overlay { position: absolute; inset: auto 0 0; padding: 64px 16px 16px; background: linear-gradient(transparent, rgba(0, 0, 0, 0.82)); }
    .gallery-label { color: #eee; font-size: 10px; letter-spacing: 0.16em; text-transform: uppercase; }
    .gallery-description { margin-top: 4px; color: var(--muted); font-size: 12px; }

    .about-layout, .contact-layout { display: grid; grid-template-columns: minmax(0, 1.1fr) minmax(0, 0.9fr); gap: 32px; }
    .about-text, .contact-copy { max-width: 620px; color: var(--muted); font-size: 15px; }
    .about-meta { color: var(--subtle); font-size: 12px; }
    .about-sign { margin-top: 32px; color: var(--muted); font-size: 11px; letter-spacing: 0.16em; text-transform: uppercase; }
    .about-sign span { display: block; margin-top: 8px; color: var(--fg); font-family: "Times New Roman", serif; font-size: 20px; letter-spacing: 0.04em; text-transform: none; }
    .contact-list { list-style: none; }
    .contact-list li + li { margin-top: 18px; }
    .contact-label { color: var(--subtle); font-size: 11px; letter-spacing: 0.16em; text-transform: uppercase; }
    .contact-value { display: inline-block; margin-top: 3px; font-size: 15px; }

    footer { display: flex; justify-content: space-between; gap: 20px; border-top: 1px solid var(--border); padding-top: 20px; color: var(--subtle); font-size: 11px; letter-spacing: 0.08em; }

    @media (max-width: 840px) {
      header { margin-bottom: 56px; }
      .hero, .about-layout, .contact-layout { grid-template-columns: 1fr; }
      .hero-image { max-width: 560px; }
      .gallery-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
    }

    @media (max-width: 560px) {
      .page { padding: 24px 16px 56px; }
      header { align-items: flex-start; flex-direction: column; gap: 16px; }
      .hero { margin-bottom: 72px; }
      section { margin-bottom: 72px; }
      .gallery-grid { grid-template-columns: 1fr; }
      .section-header, footer { align-items: flex-start; flex-direction: column; }
    }

    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { transition-duration: 0.01ms !important; }
    }
  </style>
</head>
<body>
  <div class="page">
    <header>
      <a class="logo" href="#top" aria-label="Nonchopper home">Nonchopper</a>
      <nav aria-label="メインナビゲーション">
        <ul>
          <li><a href="#top">Top</a></li>
          <li><a href="#works">Works</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section class="hero" id="top" aria-labelledby="hero-title">
        <div>
          <p class="eyebrow">Independent Creative / Japan</p>
          <h1 class="hero-title" id="hero-title">Creative<br>Portfolio</h1>
          <p class="hero-sub">Web、ビジュアル、ブランドのためのデザイン。静かに印象に残るデジタル体験をつくります。</p>
          <div class="hero-meta" aria-label="サービスカテゴリ"><span>Visual</span><span>Web</span><span>Brand</span></div>
          <div class="hero-actions"><a class="button" href="#works">View works</a><a class="button button--quiet" href="#contact">Get in touch ↗</a></div>
        </div>
        <div class="hero-image" aria-label="Nonchopperのトップビジュアル"><div class="hero-image-inner"></div><p class="hero-caption">Selected works / 2024—2025</p></div>
      </section>

      <section id="works" aria-labelledby="works-title">
        <div class="section-header"><h2 class="section-title" id="works-title">Works</h2><p class="section-sub">Selected projects</p></div>
        <div class="gallery-grid">
          <article class="gallery-item"><div class="gallery-thumb" aria-hidden="true"></div><div class="gallery-overlay"><p class="gallery-label">01 / Brand</p><p class="gallery-description">Identity and visual direction</p></div></article>
          <article class="gallery-item"><div class="gallery-thumb" aria-hidden="true"></div><div class="gallery-overlay"><p class="gallery-label">02 / Web</p><p class="gallery-description">Digital experience and interface</p></div></article>
          <article class="gallery-item"><div class="gallery-thumb" aria-hidden="true"></div><div class="gallery-overlay"><p class="gallery-label">03 / Art</p><p class="gallery-description">Image-making and direction</p></div></article>
        </div>
      </section>

      <section id="about" aria-labelledby="about-title">
        <div class="section-header"><h2 class="section-title" id="about-title">About</h2><p class="section-sub">Profile</p></div>
        <div class="about-layout"><div><p class="about-text">Nonchopperは、ブランドの個性を丁寧にすくい上げ、明快で記憶に残るビジュアルとデジタル体験へ落とし込むクリエイティブポートフォリオです。</p><p class="about-sign">Made with intention<span>Nonchopper</span></p></div><p class="about-meta">Based in Japan<br>Available for commissions and collaborations<br>Web / Visual / Brand</p></div>
      </section>

      <section id="contact" aria-labelledby="contact-title">
        <div class="section-header"><h2 class="section-title" id="contact-title">Contact</h2><p class="section-sub">Get in touch</p></div>
        <div class="contact-layout"><ul class="contact-list"><li><span class="contact-label">Email</span><br><a class="contact-value" href="mailto:hello@example.com">hello@example.com</a></li><li><span class="contact-label">Instagram</span><br><a class="contact-value" href="https://www.instagram.com/" target="_blank" rel="noreferrer">@nonchopper ↗</a></li></ul><p class="contact-copy">制作のご相談、コラボレーション、その他のお問い合わせはこちらから。内容とご希望のスケジュールを添えてご連絡ください。</p></div>
      </section>
    </main>

    <footer><span>© 2025 Nonchopper</span><span>Designed with clarity.</span></footer>
  </div>
</body>
</html>
