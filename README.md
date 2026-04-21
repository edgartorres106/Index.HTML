<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Husker Cycle Co. — MRKT 347</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Oswald:wght@400;600&family=Source+Serif+4:ital,wght@0,400;1,400&family=Inter:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --red: #CC0000;
    --red-dark: #8B0000;
    --red-light: #FF2222;
    --black: #111111;
    --off-white: #F5F0EB;
    --cream: #EDE8E1;
    --gray: #444444;
    --gray-light: #888888;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--black);
    color: var(--off-white);
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    background: rgba(17,17,17,0.95);
    border-bottom: 2px solid var(--red);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 3rem;
    height: 64px;
  }
  .nav-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.6rem;
    letter-spacing: 0.08em;
    color: var(--off-white);
  }
  .nav-logo span { color: var(--red); }
  .nav-links { display: flex; gap: 2rem; }
  .nav-links a {
    font-family: 'Oswald', sans-serif;
    font-size: 0.85rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gray-light);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--red); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 80px 2rem 4rem;
    position: relative;
    background:
      radial-gradient(ellipse 60% 40% at 50% 60%, rgba(204,0,0,0.18) 0%, transparent 70%),
      var(--black);
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image: repeating-linear-gradient(
      0deg, transparent, transparent 39px, rgba(204,0,0,0.06) 39px, rgba(204,0,0,0.06) 40px
    ), repeating-linear-gradient(
      90deg, transparent, transparent 39px, rgba(204,0,0,0.06) 39px, rgba(204,0,0,0.06) 40px
    );
    pointer-events: none;
  }
  .hero-eyebrow {
    font-family: 'Oswald', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 1.5rem;
  }
  .hero h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(5rem, 14vw, 11rem);
    line-height: 0.9;
    letter-spacing: 0.04em;
    color: var(--off-white);
    text-shadow: 0 0 80px rgba(204,0,0,0.4);
  }
  .hero h1 span { color: var(--red); display: block; }
  .hero-sub {
    font-family: 'Oswald', sans-serif;
    font-size: 1.1rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gray-light);
    margin-top: 1.5rem;
  }
  .hero-tagline {
    margin-top: 2.5rem;
    display: inline-block;
    background: var(--red);
    color: #fff;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.3rem;
    letter-spacing: 0.18em;
    padding: 0.5rem 2rem;
  }

  /* SECTIONS */
  section {
    max-width: 1100px;
    margin: 0 auto;
    padding: 6rem 2rem;
  }
  .section-label {
    font-family: 'Oswald', sans-serif;
    font-size: 0.75rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--red);
    margin-bottom: 0.75rem;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.5rem, 5vw, 4rem);
    letter-spacing: 0.05em;
    color: var(--off-white);
    margin-bottom: 2.5rem;
    line-height: 1;
  }
  .divider {
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, var(--red) 0%, transparent 100%);
    margin-bottom: 3rem;
  }

  /* ABOUT */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: start;
  }
  .about-text p {
    font-size: 1.05rem;
    line-height: 1.8;
    color: var(--cream);
    margin-bottom: 1.2rem;
  }
  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: rgba(204,0,0,0.2);
    border: 1px solid rgba(204,0,0,0.2);
  }
  .stat-box {
    background: var(--black);
    padding: 1.5rem;
    text-align: center;
  }
  .stat-box .num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.8rem;
    color: var(--red);
    display: block;
    line-height: 1;
  }
  .stat-box .lbl {
    font-family: 'Oswald', sans-serif;
    font-size: 0.75rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gray-light);
    margin-top: 0.4rem;
    display: block;
  }

  /* PRODUCTS */
  #products { background: #0a0a0a; max-width: 100%; padding: 6rem 2rem; }
  .products-inner { max-width: 1100px; margin: 0 auto; }
  .products-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
    margin-top: 2rem;
  }
  .product-card {
    background: #151515;
    border: 1px solid rgba(204,0,0,0.2);
    transition: border-color 0.3s, transform 0.3s;
    overflow: hidden;
  }
  .product-card:hover {
    border-color: var(--red);
    transform: translateY(-4px);
  }
  .product-img-wrap {
    background: #1a1a1a;
    padding: 2rem 1.5rem 1.5rem;
    text-align: center;
    border-bottom: 2px solid var(--red);
  }
  .product-icon {
    font-size: 4rem;
    line-height: 1;
  }
  .product-sku {
    font-family: 'Oswald', sans-serif;
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    color: var(--gray-light);
    margin-top: 0.5rem;
  }
  .product-body { padding: 1.5rem; }
  .product-name {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.5rem;
    letter-spacing: 0.06em;
    color: var(--off-white);
    margin-bottom: 0.75rem;
    line-height: 1.1;
  }
  .product-desc {
    font-size: 0.88rem;
    line-height: 1.7;
    color: var(--gray-light);
    margin-bottom: 1.2rem;
  }
  .product-features {
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }
  .product-features li {
    font-family: 'Oswald', sans-serif;
    font-size: 0.7rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--red);
    border: 1px solid rgba(204,0,0,0.4);
    padding: 0.25rem 0.6rem;
  }

  /* PERSONAS */
  .personas-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }
  .persona-card {
    border-left: 4px solid var(--red);
    background: #111;
    padding: 2rem;
  }
  .persona-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.8rem;
    letter-spacing: 0.05em;
    color: var(--red);
    margin-bottom: 0.25rem;
  }
  .persona-age {
    font-family: 'Oswald', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gray-light);
    margin-bottom: 1rem;
  }
  .persona-card p {
    font-size: 0.92rem;
    line-height: 1.75;
    color: var(--cream);
  }

  /* MARKETING */
  .goals-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    margin-bottom: 3rem;
  }
  .goal-card {
    background: #111;
    padding: 2rem;
    border-top: 3px solid var(--red);
  }
  .goal-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 4rem;
    color: rgba(204,0,0,0.15);
    line-height: 1;
    margin-bottom: -0.5rem;
  }
  .goal-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.5rem;
    letter-spacing: 0.05em;
    color: var(--off-white);
    margin-bottom: 0.75rem;
  }
  .goal-card p, .goal-card ul {
    font-size: 0.9rem;
    line-height: 1.75;
    color: var(--cream);
  }
  .goal-card ul { padding-left: 1.2rem; }
  .goal-card ul li { margin-bottom: 0.4rem; }

  /* PRICING */
  .pricing-strip {
    background: var(--red);
    padding: 3rem;
    margin-top: 2rem;
  }
  .pricing-strip h3 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem;
    letter-spacing: 0.06em;
    color: #fff;
    margin-bottom: 1.5rem;
  }
  .pricing-items {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  .pricing-item {
    background: rgba(0,0,0,0.25);
    padding: 1.25rem;
  }
  .pricing-discount {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.5rem;
    color: #fff;
    line-height: 1;
  }
  .pricing-who {
    font-family: 'Oswald', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.7);
    margin-top: 0.4rem;
  }

  /* TEAM */
  .team-grid {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 1rem;
  }
  .team-card {
    text-align: center;
    padding: 1.5rem 0.5rem;
    border: 1px solid rgba(204,0,0,0.2);
    background: #111;
    transition: background 0.2s;
  }
  .team-card:hover { background: #1a0000; }
  .team-initial {
    width: 56px;
    height: 56px;
    border-radius: 50%;
    background: var(--red-dark);
    border: 2px solid var(--red);
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 1rem;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.4rem;
    color: var(--off-white);
  }
  .team-name {
    font-family: 'Oswald', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.05em;
    color: var(--off-white);
    text-transform: uppercase;
  }
  .team-role {
    font-size: 0.75rem;
    color: var(--gray-light);
    margin-top: 0.25rem;
  }

  /* FOOTER */
  footer {
    background: #080808;
    border-top: 2px solid var(--red);
    text-align: center;
    padding: 3rem 2rem;
  }
  footer .foot-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.5rem;
    letter-spacing: 0.1em;
    color: var(--red);
    margin-bottom: 0.5rem;
  }
  footer p {
    font-family: 'Oswald', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gray-light);
  }

  /* Full-bleed bg section */
  .bg-section {
    background: #0a0a0a;
    width: 100%;
  }
  .bg-section section { max-width: 1100px; margin: 0 auto; }

  @media (max-width: 768px) {
    nav { padding: 0 1.5rem; }
    .nav-links { display: none; }
    .hero h1 { font-size: 4rem; }
    .about-grid, .personas-grid, .goals-grid, .products-grid, .pricing-items { grid-template-columns: 1fr; }
    .team-grid { grid-template-columns: repeat(2, 1fr); }
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo">Husker <span>Cycle</span> Co.</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#products">Products</a>
    <a href="#personas">Customers</a>
    <a href="#marketing">Marketing</a>
    <a href="#team">Team</a>
  </div>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-eyebrow">MRKT 347 — Final Project</div>
  <h1>Husker<span>Cycle Co.</span></h1>
  <div class="hero-sub">Lincoln, Nebraska · Est. 2025</div>
  <div class="hero-tagline">Ride Lincoln. Ride Husker.</div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="section-label">01 — Our Brand</div>
  <div class="section-title">Built for Urban Riders</div>
  <div class="divider"></div>
  <div class="about-grid">
    <div class="about-text">
      <p>Husker Cycle Co. manufactures lightweight commuter bicycles built for urban riders. We combine Husker pride with modern cycling culture, offering bikes that are as bold as they are functional.</p>
      <p>Our mission is to make eco-friendly transportation accessible to everyone in Lincoln — from students commuting to campus to teens exploring the city with friends.</p>
      <p>Every Husker bike comes with custom frame color options, ergonomic design, lifetime tune-ups, and access to our weekend cycling workshops for beginners.</p>
    </div>
    <div class="about-stats">
      <div class="stat-box">
        <span class="num">3</span>
        <span class="lbl">Product Lines</span>
      </div>
      <div class="stat-box">
        <span class="num">15%</span>
        <span class="lbl">Student Discount</span>
      </div>
      <div class="stat-box">
        <span class="num">∞</span>
        <span class="lbl">Lifetime Tune-Ups</span>
      </div>
      <div class="stat-box">
        <span class="num">LNK</span>
        <span class="lbl">Based in Lincoln</span>
      </div>
    </div>
  </div>
</section>

<!-- PRODUCTS -->
<div style="background:#0a0a0a; width:100%; padding: 6rem 2rem;" id="products">
  <div style="max-width:1100px; margin:0 auto;">
    <div class="section-label">02 — Product Catalog</div>
    <div class="section-title">Our Lineup</div>
    <div class="divider"></div>
    <div class="products-grid">

      <div class="product-card">
        <div class="product-img-wrap">
          <div class="product-icon">🚲</div>
          <div class="product-sku">SKU: HCC-URB-001</div>
        </div>
        <div class="product-body">
          <div class="product-name">Husker Urban Commuter Bike</div>
          <p class="product-desc">Designed for everyday riders in Lincoln. Lightweight aluminum frame, ergonomic seating, and custom frame colors — perfect for getting to class or cruising downtown.</p>
          <ul class="product-features">
            <li>Lightweight Frame</li>
            <li>Ergonomic Design</li>
            <li>Custom Colors</li>
            <li>Lifetime Tune-Ups</li>
          </ul>
        </div>
      </div>

      <div class="product-card">
        <div class="product-img-wrap">
          <div class="product-icon">🔴</div>
          <div class="product-sku">SKU: HCC-CUS-002</div>
        </div>
        <div class="product-body">
          <div class="product-name">Husker Custom Edition Bike</div>
          <p class="product-desc">Stand out on every ride. Built for riders who want performance and personality — upgraded materials, enhanced comfort components, and exclusive custom color designs.</p>
          <ul class="product-features">
            <li>Premium Materials</li>
            <li>Custom Designs</li>
            <li>Upgraded Components</li>
            <li>Lifetime Tune-Ups</li>
          </ul>
        </div>
      </div>

      <div class="product-card">
        <div class="product-img-wrap">
          <div class="product-icon">⛑️</div>
          <div class="product-sku">SKU: HCC-ACC-003</div>
        </div>
        <div class="product-body">
          <div class="product-name">Husker Rider Starter Kit</div>
          <p class="product-desc">Everything you need to start riding with confidence. Includes a helmet, bike lock, and safety lights. Pair with any Husker bike and join our weekend cycling workshops.</p>
          <ul class="product-features">
            <li>Safety First</li>
            <li>Secure Your Ride</li>
            <li>Front &amp; Rear Lights</li>
            <li>Community &amp; Support</li>
          </ul>
        </div>
      </div>

    </div>
  </div>
</div>

<!-- PERSONAS -->
<section id="personas">
  <div class="section-label">03 — Customer Profiles</div>
  <div class="section-title">Who We Ride For</div>
  <div class="divider"></div>
  <div class="personas-grid">
    <div class="persona-card">
      <div class="persona-title">College Students</div>
      <div class="persona-age">Ages 18–24 · Lincoln, NE</div>
      <p>Full-time students balancing academics with part-time work. Budget-conscious and convenience-driven, they value easy commuting and active outdoor lifestyles. They're adventurous, love exploring campus and the city, and seek experiences both on and off campus.</p>
    </div>
    <div class="persona-card">
      <div class="persona-title">Teens</div>
      <div class="persona-age">Ages 13–16 · Lincoln, NE</div>
      <p>Highly social and trend-driven, this group loves spending time outdoors — biking, hanging out in parks, and attending local events. They prioritize fun, accessible activities with friends and family, and are drawn to products that reflect their personality.</p>
    </div>
  </div>
</section>

<!-- MARKETING -->
<div style="background:#0a0a0a; width:100%; padding: 6rem 2rem;" id="marketing">
  <div style="max-width:1100px; margin:0 auto;">
    <div class="section-label">04 — Strategy</div>
    <div class="section-title">Marketing &amp; Communication</div>
    <div class="divider"></div>
    <div class="goals-grid">
      <div class="goal-card">
        <div class="goal-num">01</div>
        <div class="goal-title">Increase Brand Awareness</div>
        <p style="margin-bottom:0.75rem;">Market Penetration + Pull Strategy</p>
        <ul>
          <li>Host a low-cost bike club to build brand familiarity</li>
          <li>Partner with local cyclists as influencers</li>
          <li>Engage audiences on Instagram and TikTok</li>
        </ul>
      </div>
      <div class="goal-card">
        <div class="goal-num">02</div>
        <div class="goal-title">Increase Bike Sales</div>
        <p style="margin-bottom:0.75rem;">Product Differentiation + Value-Based Marketing</p>
        <ul>
          <li>Introduce a try-before-you-buy system</li>
          <li>Offer limited-time promotions</li>
          <li>Partner with local businesses</li>
          <li>Highlight customization options in ads</li>
          <li>Offer long-term warranties (1–3 years)</li>
        </ul>
      </div>
    </div>

    <!-- PRICING -->
    <div class="pricing-strip">
      <h3>Differentiated Pricing</h3>
      <div class="pricing-items">
        <div class="pricing-item">
          <div class="pricing-discount">15% Off</div>
          <div class="pricing-who">Students with valid ID</div>
        </div>
        <div class="pricing-item">
          <div class="pricing-discount">20% Off</div>
          <div class="pricing-who">New cyclists</div>
        </div>
        <div class="pricing-item">
          <div class="pricing-discount">Premium+</div>
          <div class="pricing-who">Custom colors &amp; limited editions</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- TEAM -->
<section id="team">
  <div class="section-label">05 — Our Team</div>
  <div class="section-title">MRKT 347 Group</div>
  <div class="divider"></div>
  <div class="team-grid">
    <div class="team-card">
      <div class="team-initial">CB</div>
      <div class="team-name">Cassie Butts</div>
      <div class="team-role">Team Member</div>
    </div>
    <div class="team-card">
      <div class="team-initial">ET</div>
      <div class="team-name">Edgar Torres</div>
      <div class="team-role">Team Member</div>
    </div>
    <div class="team-card">
      <div class="team-initial">BD</div>
      <div class="team-name">Bailey Dorfmeyer</div>
      <div class="team-role">Team Member</div>
    </div>
    <div class="team-card">
      <div class="team-initial">BP</div>
      <div class="team-name">Blake Perchal</div>
      <div class="team-role">Team Member</div>
    </div>
    <div class="team-card">
      <div class="team-initial">RB</div>
      <div class="team-name">Rylan Birkby</div>
      <div class="team-role">Team Member</div>
    </div>
  </div>
</section>

<footer>
  <div class="foot-logo">Husker Cycle Co.</div>
  <p>MRKT 347 · University of Nebraska–Lincoln · 2025</p>
  <p style="margin-top:0.75rem; font-size:0.7rem;">Ride Sustainable. Ride Husker.</p>
</footer>

</body>
</html>
