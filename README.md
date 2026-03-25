<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Canetas Emagrecedoras — Camilla Compagnoni</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --gold: #C49A3C;
    --gold-light: #E8C97A;
    --gold-pale: #F5E6C0;
    --dark: #0E0D0B;
    --dark-2: #1A1916;
    --dark-3: #252320;
    --cream: #F7F4EE;
    --cream-2: #EDE9DF;
    --text-light: #C8C4BB;
    --text-muted: #88867F;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--dark);
    color: var(--cream);
    overflow-x: hidden;
  }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    background: var(--dark);
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 80px 24px 60px;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background: radial-gradient(ellipse 70% 50% at 50% 0%, rgba(196,154,60,0.12) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-tag {
    font-family: 'DM Sans', sans-serif;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp 0.8s ease forwards 0.2s;
  }

  .hero-title {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(52px, 10vw, 96px);
    font-weight: 300;
    line-height: 0.95;
    color: var(--cream);
    margin-bottom: 16px;
    opacity: 0;
    animation: fadeUp 0.9s ease forwards 0.4s;
  }

  .hero-title em {
    font-style: italic;
    color: var(--gold-light);
    display: block;
  }

  .hero-subtitle {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(18px, 3vw, 24px);
    font-weight: 300;
    color: var(--text-light);
    max-width: 520px;
    line-height: 1.5;
    margin-bottom: 48px;
    opacity: 0;
    animation: fadeUp 1s ease forwards 0.6s;
  }

  .hero-cta {
    display: inline-block;
    background: var(--gold);
    color: var(--dark);
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    text-decoration: none;
    padding: 18px 48px;
    transition: background 0.2s, transform 0.2s;
    opacity: 0;
    animation: fadeUp 1s ease forwards 0.8s;
  }

  .hero-cta:hover {
    background: var(--gold-light);
    transform: translateY(-2px);
  }

  .hero-scroll {
    position: absolute;
    bottom: 32px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    opacity: 0;
    animation: fadeUp 1s ease forwards 1.2s;
  }

  .hero-scroll span {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--text-muted);
  }

  .scroll-line {
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, var(--gold), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }

  /* ── AUTHOR STRIP ── */
  .author-strip {
    background: var(--dark-2);
    border-top: 1px solid rgba(196,154,60,0.2);
    border-bottom: 1px solid rgba(196,154,60,0.2);
    padding: 32px 24px;
    text-align: center;
  }

  .author-strip p {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(16px, 2.5vw, 20px);
    font-weight: 300;
    font-style: italic;
    color: var(--text-light);
    max-width: 700px;
    margin: 0 auto;
    line-height: 1.6;
  }

  .author-strip strong {
    color: var(--gold-light);
    font-style: normal;
    font-weight: 400;
  }

  /* ── ABOUT ── */
  .about {
    padding: 100px 24px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .section-label {
    font-size: 10px;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 16px;
  }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }

  .about-photo {
    position: relative;
  }

  .photo-placeholder {
    width: 100%;
    aspect-ratio: 3/4;
    background: var(--dark-3);
    border: 1px solid rgba(196,154,60,0.2);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 12px;
    color: var(--text-muted);
    font-size: 13px;
    text-align: center;
    padding: 24px;
    cursor: pointer;
    transition: border-color 0.2s;
  }

  .photo-placeholder:hover {
    border-color: rgba(196,154,60,0.5);
  }

  .photo-placeholder svg {
    opacity: 0.4;
  }

  .photo-corner {
    position: absolute;
    width: 40px;
    height: 40px;
    border-color: var(--gold);
    border-style: solid;
    border-width: 0;
  }

  .photo-corner.tl { top: -8px; left: -8px; border-top-width: 2px; border-left-width: 2px; }
  .photo-corner.br { bottom: -8px; right: -8px; border-bottom-width: 2px; border-right-width: 2px; }

  .about-content h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(36px, 5vw, 52px);
    font-weight: 300;
    line-height: 1.1;
    margin-bottom: 24px;
    color: var(--cream);
  }

  .about-content h2 em {
    font-style: italic;
    color: var(--gold-light);
  }

  .about-content p {
    font-size: 15px;
    font-weight: 300;
    line-height: 1.8;
    color: var(--text-light);
    margin-bottom: 16px;
  }

  .about-stats {
    display: flex;
    gap: 32px;
    margin-top: 36px;
    padding-top: 36px;
    border-top: 1px solid rgba(255,255,255,0.08);
  }

  .stat-item {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .stat-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 42px;
    font-weight: 300;
    color: var(--gold-light);
    line-height: 1;
  }

  .stat-label {
    font-size: 11px;
    color: var(--text-muted);
    letter-spacing: 0.1em;
  }

  /* ── WHAT YOU FIND ── */
  .content-section {
    background: var(--dark-2);
    padding: 100px 24px;
  }

  .content-inner {
    max-width: 1100px;
    margin: 0 auto;
  }

  .content-header {
    text-align: center;
    margin-bottom: 64px;
  }

  .content-header h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(36px, 5vw, 56px);
    font-weight: 300;
    color: var(--cream);
    line-height: 1.1;
  }

  .content-header h2 em {
    font-style: italic;
    color: var(--gold-light);
  }

  .chapters-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 1px;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.06);
  }

  .chapter-card {
    background: var(--dark-2);
    padding: 40px 32px;
    transition: background 0.2s;
  }

  .chapter-card:hover {
    background: var(--dark-3);
  }

  .chapter-number {
    font-family: 'Cormorant Garamond', serif;
    font-size: 64px;
    font-weight: 300;
    color: rgba(196,154,60,0.15);
    line-height: 1;
    margin-bottom: 16px;
  }

  .chapter-card h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px;
    font-weight: 400;
    color: var(--cream);
    margin-bottom: 12px;
  }

  .chapter-card p {
    font-size: 13px;
    line-height: 1.7;
    color: var(--text-muted);
    font-weight: 300;
  }

  /* ── QUOTES / SCIENCE ── */
  .science-section {
    padding: 100px 24px;
    max-width: 900px;
    margin: 0 auto;
    text-align: center;
  }

  .big-quote {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(28px, 4vw, 44px);
    font-weight: 300;
    font-style: italic;
    line-height: 1.4;
    color: var(--cream);
    position: relative;
    padding: 0 40px;
    margin-bottom: 32px;
  }

  .big-quote::before, .big-quote::after {
    content: '"';
    font-size: 80px;
    color: rgba(196,154,60,0.2);
    position: absolute;
    font-style: normal;
    line-height: 1;
  }

  .big-quote::before { top: -20px; left: 0; }
  .big-quote::after { content: '"'; bottom: -40px; right: 0; }

  .quote-source {
    font-size: 12px;
    letter-spacing: 0.15em;
    color: var(--gold);
    text-transform: uppercase;
  }

  /* ── PILLS / KEY POINTS ── */
  .pills-section {
    background: var(--dark-3);
    padding: 80px 24px;
    border-top: 1px solid rgba(196,154,60,0.15);
    border-bottom: 1px solid rgba(196,154,60,0.15);
  }

  .pills-inner {
    max-width: 900px;
    margin: 0 auto;
    text-align: center;
  }

  .pills-inner h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(28px, 4vw, 40px);
    font-weight: 300;
    color: var(--cream);
    margin-bottom: 40px;
  }

  .pills-inner h2 em {
    font-style: italic;
    color: var(--gold-light);
  }

  .pills-list {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
  }

  .pill {
    background: transparent;
    border: 1px solid rgba(196,154,60,0.3);
    color: var(--text-light);
    font-size: 13px;
    padding: 10px 20px;
    font-weight: 300;
    letter-spacing: 0.05em;
    transition: border-color 0.2s, color 0.2s;
  }

  .pill:hover {
    border-color: var(--gold);
    color: var(--gold-light);
  }

  /* ── VIDEO PLACEHOLDER ── */
  .video-section {
    padding: 100px 24px;
    background: var(--dark);
    text-align: center;
  }

  .video-inner {
    max-width: 800px;
    margin: 0 auto;
  }

  .video-inner h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(32px, 4vw, 48px);
    font-weight: 300;
    color: var(--cream);
    margin-bottom: 16px;
  }

  .video-inner p {
    font-size: 14px;
    color: var(--text-muted);
    margin-bottom: 40px;
    font-weight: 300;
  }

  .video-placeholder {
    width: 100%;
    aspect-ratio: 16/9;
    background: var(--dark-3);
    border: 1px dashed rgba(196,154,60,0.25);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 16px;
    color: var(--text-muted);
    font-size: 13px;
  }

  .video-placeholder svg {
    opacity: 0.3;
  }

  /* ── SUBSTANCES TABLE ── */
  .substances {
    padding: 100px 24px;
    background: var(--dark-2);
  }

  .substances-inner {
    max-width: 1000px;
    margin: 0 auto;
  }

  .substances-inner h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(32px, 4vw, 48px);
    font-weight: 300;
    color: var(--cream);
    text-align: center;
    margin-bottom: 8px;
  }

  .substances-inner > p {
    text-align: center;
    color: var(--text-muted);
    font-size: 13px;
    margin-bottom: 48px;
  }

  .substance-cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }

  .substance-card {
    background: var(--dark);
    border: 1px solid rgba(255,255,255,0.06);
    padding: 36px 28px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s;
  }

  .substance-card:hover {
    border-color: rgba(196,154,60,0.3);
  }

  .substance-card.featured {
    border-color: rgba(196,154,60,0.4);
  }

  .substance-card.featured::before {
    content: 'Utilizada pela autora';
    position: absolute;
    top: 0; right: 0;
    background: var(--gold);
    color: var(--dark);
    font-size: 9px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 5px 12px;
    font-weight: 500;
  }

  .substance-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 28px;
    font-weight: 400;
    color: var(--gold-light);
    margin-bottom: 8px;
  }

  .substance-type {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-bottom: 20px;
  }

  .substance-loss {
    font-family: 'Cormorant Garamond', serif;
    font-size: 48px;
    font-weight: 300;
    color: var(--cream);
    line-height: 1;
    margin-bottom: 4px;
  }

  .substance-loss-label {
    font-size: 10px;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .substance-freq {
    font-size: 12px;
    color: var(--text-light);
    padding-top: 16px;
    border-top: 1px solid rgba(255,255,255,0.06);
  }

  /* ── BIG CTA ── */
  .big-cta {
    padding: 120px 24px;
    background: var(--dark);
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .big-cta::before {
    content: '';
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(196,154,60,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .big-cta-inner {
    max-width: 700px;
    margin: 0 auto;
    position: relative;
    z-index: 1;
  }

  .big-cta h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(42px, 7vw, 72px);
    font-weight: 300;
    line-height: 1.05;
    color: var(--cream);
    margin-bottom: 24px;
  }

  .big-cta h2 em {
    font-style: italic;
    color: var(--gold-light);
  }

  .big-cta p {
    font-size: 15px;
    color: var(--text-light);
    line-height: 1.7;
    font-weight: 300;
    max-width: 520px;
    margin: 0 auto 48px;
  }

  .price-box {
    background: var(--dark-2);
    border: 1px solid rgba(196,154,60,0.3);
    padding: 40px 48px;
    margin-bottom: 32px;
    display: inline-block;
    min-width: 320px;
  }

  .price-label {
    font-size: 11px;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 8px;
  }

  .price-value {
    font-family: 'Cormorant Garamond', serif;
    font-size: 56px;
    font-weight: 300;
    color: var(--cream);
    line-height: 1;
    margin-bottom: 4px;
  }

  .price-desc {
    font-size: 12px;
    color: var(--text-muted);
  }

  .buy-btn {
    display: block;
    background: var(--gold);
    color: var(--dark);
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    text-decoration: none;
    padding: 20px 64px;
    transition: background 0.2s, transform 0.15s;
    cursor: pointer;
    border: none;
    margin: 0 auto;
    width: fit-content;
  }

  .buy-btn:hover {
    background: var(--gold-light);
    transform: translateY(-2px);
  }

  .security-note {
    margin-top: 20px;
    font-size: 12px;
    color: var(--text-muted);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
  }

  /* ── DISCLAIMER ── */
  .disclaimer {
    background: var(--dark-2);
    border-top: 1px solid rgba(255,255,255,0.05);
    padding: 48px 24px;
  }

  .disclaimer-inner {
    max-width: 700px;
    margin: 0 auto;
    text-align: center;
  }

  .disclaimer-inner p {
    font-size: 12px;
    color: var(--text-muted);
    line-height: 1.8;
    font-weight: 300;
  }

  /* ── FOOTER ── */
  footer {
    background: var(--dark);
    border-top: 1px solid rgba(255,255,255,0.05);
    padding: 32px 24px;
    text-align: center;
  }

  footer p {
    font-size: 12px;
    color: var(--text-muted);
  }

  footer span {
    color: var(--gold);
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes scrollPulse {
    0%, 100% { opacity: 0.4; }
    50% { opacity: 1; }
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 768px) {
    .about-grid { grid-template-columns: 1fr; gap: 48px; }
    .substance-cards { grid-template-columns: 1fr; }
    .about-stats { gap: 20px; }
    .big-quote { padding: 0 20px; }
    .price-box { min-width: 280px; padding: 32px 32px; }
  }

  @media (max-width: 540px) {
    .chapters-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- ── HERO ── -->
<section class="hero">
  <p class="hero-tag">Informação Clara · Ciência Explicada</p>
  <h1 class="hero-title">
    Canetas<br>
    <em>Emagrecedoras</em>
  </h1>
  <p class="hero-subtitle">O que você precisa saber antes de usar — e minha experiência com 37 quilos a menos.</p>
  <a href="SEU_LINK_KIWIFY_AQUI" class="hero-cta" target="_blank" rel="noopener">Quero o e-book</a>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span>Explorar</span>
  </div>
</section>

<!-- ── AUTHOR STRIP ── -->
<div class="author-strip">
  <p>Escrito por <strong>Camilla Compagnoni</strong> — jornalista, especialista em neurociência e comportamento emocional, e alguém que viveu na pele o que a ciência explica.</p>
</div>

<!-- ── ABOUT ── -->
<section class="about">
  <div class="about-grid">

    <div class="about-photo">
      <div class="photo-placeholder" id="photo-area">
        <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="12" cy="10" r="3"/><path d="M7 21v-1a5 5 0 0 1 10 0v1"/></svg>
        <span>Foto da Camilla<br><small style="font-size:11px; opacity:0.6;">Envie sua foto para adicionar aqui</small></span>
      </div>
      <div class="photo-corner tl"></div>
      <div class="photo-corner br"></div>
    </div>

    <div class="about-content">
      <p class="section-label">Sobre a autora</p>
      <h2>Uma história<br>que <em>começa</em><br>com 137 kg</h2>
      <p>Já pesei 137 quilos. Passei por cirurgia bariátrica, dietas de todas as modas, restrições que esgotam o corpo e a mente. Por anos, busquei uma resposta que a ciência já tinha, mas que ninguém me explicava com clareza.</p>
      <p>Sou jornalista com pós-graduação em neurociência e comportamento emocional. Quando as chamadas "canetas emagrecedoras" viraram assunto, eu vi promessas exageradas, críticas rasas — e muito pouco conteúdo responsável.</p>
      <p>Esse e-book nasceu dessa lacuna: informação real, linguagem acessível, e a vivência de quem usou o tratamento com acompanhamento médico.</p>

      <div class="about-stats">
        <div class="stat-item">
          <span class="stat-number">37 kg</span>
          <span class="stat-label">perdidos no tratamento</span>
        </div>
        <div class="stat-item">
          <span class="stat-number">7</span>
          <span class="stat-label">capítulos de conteúdo</span>
        </div>
        <div class="stat-item">
          <span class="stat-number">+20</span>
          <span class="stat-label">referências científicas</span>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ── WHAT'S INSIDE ── -->
<section class="content-section">
  <div class="content-inner">
    <div class="content-header">
      <p class="section-label">O que você vai encontrar</p>
      <h2>7 capítulos que<br><em>ninguém te contou</em></h2>
    </div>

    <div class="chapters-grid">
      <div class="chapter-card">
        <div class="chapter-number">01</div>
        <h3>Como tudo começou: a ciência por trás do fenômeno</h3>
        <p>A descoberta dos hormônios intestinais GLP-1 e GIP, e como pesquisadores encontraram o emagrecimento enquanto estudavam o diabetes.</p>
      </div>
      <div class="chapter-card">
        <div class="chapter-number">02</div>
        <h3>Como essas medicações funcionam no corpo</h3>
        <p>Grelina, leptina, hipotálamo. A fome não é falta de força de vontade — é um diálogo hormonal entre o intestino e o cérebro.</p>
      </div>
      <div class="chapter-card">
        <div class="chapter-number">03</div>
        <h3>Quais são as substâncias disponíveis hoje</h3>
        <p>Liraglutida, Semaglutida e Tirzepatida: mecanismo, eficácia em estudos clínicos, frequência de uso e contraindicações.</p>
      </div>
      <div class="chapter-card">
        <div class="chapter-number">04</div>
        <h3>Efeitos colaterais e riscos</h3>
        <p>Do que é mais comum ao que é menos falado: queda de cabelo, sensação de frio, pedra na vesícula, tolerância ao álcool e mais.</p>
      </div>
      <div class="chapter-card">
        <div class="chapter-number">05</div>
        <h3>O desmame e o pós: o que acontece depois?</h3>
        <p>Uma das partes menos discutidas do tratamento. O que estudos mostram sobre a retomada de peso e o que é necessário para manter o resultado.</p>
      </div>
      <div class="chapter-card">
        <div class="chapter-number">06</div>
        <h3>Minha experiência: entre tentativas e consciência</h3>
        <p>Os bastidores reais — efeitos que senti, o que ajudou, o que dificultou, o custo financeiro e o que aprendi sobre o tratamento de longo prazo.</p>
      </div>
      <div class="chapter-card">
        <div class="chapter-number">07</div>
        <h3>O impacto emocional do emagrecimento</h3>
        <p>Emagrecer mexe com a identidade. O que acontece com a mente quando o corpo muda — e por que o acompanhamento emocional é insubstituível.</p>
      </div>
    </div>

  </div>
</section>

<!-- ── QUOTE ── -->
<section class="science-section">
  <p class="section-label">Da autora</p>
  <p class="big-quote">A fome não é apenas vontade. Ela é, antes de tudo, um diálogo hormonal entre o intestino e o cérebro.</p>
  <p class="quote-source">— Camilla Compagnoni, Canetas Emagrecedoras</p>
</section>

<!-- ── PILLS ── -->
<section class="pills-section">
  <div class="pills-inner">
    <h2>Você vai encontrar respostas para <em>essas perguntas</em></h2>
    <div class="pills-list">
      <span class="pill">Funciona mesmo?</span>
      <span class="pill">É seguro?</span>
      <span class="pill">Quais são os riscos reais?</span>
      <span class="pill">Todo mundo pode usar?</span>
      <span class="pill">O que acontece depois que para?</span>
      <span class="pill">Preciso mudar minha alimentação?</span>
      <span class="pill">Qual a diferença entre as substâncias?</span>
      <span class="pill">Quanto tempo dura o tratamento?</span>
      <span class="pill">Posso engordar tudo de volta?</span>
      <span class="pill">O peso emocional do emagrecimento</span>
    </div>
  </div>
</section>

<!-- ── VIDEO PLACEHOLDER ── -->
<section class="video-section">
  <div class="video-inner">
    <p class="section-label">Vídeo de apresentação</p>
    <h2>Ouça da própria <em>Camilla</em></h2>
    <p>Em breve: vídeo de divulgação da autora sobre o e-book.</p>
    <div class="video-placeholder">
      <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round">
        <circle cx="12" cy="12" r="10"/>
        <polygon points="10 8 16 12 10 16 10 8"/>
      </svg>
      <span>Vídeo será adicionado em breve</span>
    </div>
  </div>
</section>

<!-- ── SUBSTANCES ── -->
<section class="substances">
  <div class="substances-inner">
    <p class="section-label" style="text-align:center">O que o e-book cobre</p>
    <h2>As três substâncias<br>em detalhe</h2>
    <p>Resultados de estudos clínicos controlados. Médias estatísticas — resultados individuais variam.</p>

    <div class="substance-cards">
      <div class="substance-card">
        <div class="substance-name">Liraglutida</div>
        <div class="substance-type">Agonista GLP-1 · Uso diário</div>
        <div class="substance-loss">~8%</div>
        <div class="substance-loss-label">perda média em 56 semanas</div>
        <div class="substance-freq">Estudo SCALE</div>
      </div>
      <div class="substance-card">
        <div class="substance-name">Semaglutida</div>
        <div class="substance-type">Análogo GLP-1 · Uso semanal</div>
        <div class="substance-loss">~15%</div>
        <div class="substance-loss-label">perda média em 68 semanas</div>
        <div class="substance-freq">Estudo STEP 1 · N Engl J Med, 2021</div>
      </div>
      <div class="substance-card featured">
        <div class="substance-name">Tirzepatida</div>
        <div class="substance-type">Agonista GLP-1 + GIP · Uso semanal</div>
        <div class="substance-loss">15–21%</div>
        <div class="substance-loss-label">perda média em 72 semanas</div>
        <div class="substance-freq">SURMOUNT-1 · 2022</div>
      </div>
    </div>
  </div>
</section>

<!-- ── BIG CTA ── -->
<section class="big-cta">
  <div class="big-cta-inner">
    <p class="section-label">Acesso imediato</p>
    <h2>Decisão consciente<br>é sempre <em>melhor</em><br>que decisão impulsiva.</h2>
    <p>Antes de tomar qualquer decisão sobre seu corpo e sua saúde, você merece entender o cenário completo. Esse e-book foi feito pra isso.</p>

    <div class="price-box">
      <div class="price-label">E-book digital</div>
      <div class="price-value"><!-- INSIRA O PREÇO AQUI --></div>
      <div class="price-desc">Acesso imediato após a compra · Formato PDF</div>
    </div>

    <br>

    <a href="SEU_LINK_KIWIFY_AQUI" class="buy-btn" target="_blank" rel="noopener">
      Comprar agora
    </a>

    <div class="security-note">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="11" width="18" height="11" rx="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
      Compra segura via Kiwify · Pagamento processado com criptografia
    </div>
  </div>
</section>

<!-- ── DISCLAIMER ── -->
<div class="disclaimer">
  <div class="disclaimer-inner">
    <p><strong style="color: var(--text-light); font-weight:400;">Aviso importante:</strong> Este material possui caráter exclusivamente informativo e educativo. Os medicamentos mencionados são de prescrição e devem ser utilizados somente sob orientação de profissional habilitado. Este e-book não substitui consulta médica, avaliação clínica individualizada ou acompanhamento profissional. Resultados descritos em estudos científicos representam médias estatísticas e não configuram garantia de resultados individuais.</p>
  </div>
</div>

<!-- ── FOOTER ── -->
<footer>
  <p>© 2026 <span>Camilla Compagnoni</span> · Todos os direitos reservados</p>
</footer>

</body>
</html>
