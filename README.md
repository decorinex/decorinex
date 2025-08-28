<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Decorinex Real Estate</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap');

    /* Reset & base */
    *, *::before, *::after {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: linear-gradient(135deg, #e3f2fd, #bbdefb);
      color: #1b2735;
      line-height: 1.6;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      scroll-behavior: smooth;
    }

    a {
      outline-offset: 3px;
      outline-color: transparent;
      transition: outline-color 0.3s ease;
    }
    a:focus-visible {
      outline-color: #ffca28;
    }

    /* HEADER */
    header {
      background: linear-gradient(90deg, #0d47a1, #1976d2);
      padding: 30px 20px;
      text-align: center;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      color: #fff;
      letter-spacing: 4px;
      font-weight: 800;
      font-size: 3rem;
      text-transform: uppercase;
      user-select: none;
      position: sticky;
      top: 0;
      z-index: 100;
      text-shadow: 0 2px 6px rgba(0,0,0,0.25);
    }

    /* NAVIGATION */
    nav {
      background: #1565c0;
      display: flex;
      justify-content: center;
      gap: 3rem;
      padding: 18px 15px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      transition: background 0.3s ease;
      flex-wrap: wrap;
      user-select: none;
    }

    nav a {
      color: #bbdefb;
      text-decoration: none;
      font-weight: 600;
      font-size: 1.25rem;
      position: relative;
      padding: 6px 0;
      transition: color 0.3s ease;
      white-space: nowrap;
      letter-spacing: 0.05em;
    }

    nav a::after {
      content: '';
      position: absolute;
      width: 0;
      height: 3px;
      background: #ffca28;
      left: 0;
      bottom: -8px;
      transition: width 0.35s cubic-bezier(0.4, 0, 0.2, 1);
      border-radius: 3px;
    }

    nav a:hover, nav a:focus {
      color: #fff176;
    }

    nav a:hover::after, nav a:focus::after {
      width: 100%;
    }

    /* MAIN CONTENT SECTIONS */
    section {
      max-width: 900px;
      background: rgba(255 255 255 / 0.95);
      margin: 60px auto;
      padding: 45px 40px;
      border-radius: 24px;
      box-shadow: 0 15px 35px rgba(33, 150, 243, 0.18);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    section:hover {
      transform: translateY(-8px);
      box-shadow: 0 25px 50px rgba(33, 150, 243, 0.35);
    }

    .section-title {
      font-size: 2.8rem;
      margin-bottom: 30px;
      text-align: center;
      color: #0d47a1;
      font-weight: 800;
      letter-spacing: 0.1em;
      text-shadow: 1px 1px 8px rgba(0,0,0,0.08);
    }

    /* ABOUT US */
    .about p {
      font-size: 1.25rem;
      line-height: 1.9;
      color: #2c3e50;
      text-align: justify;
      letter-spacing: 0.01em;
    }

    .about strong {
      color: #1565c0;
      font-weight: 700;
    }

    /* SERVICES */
    .services ul {
      list-style: none;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 25px;
      padding: 0;
    }

    .services li {
      background: #eaf4fd;
      border-radius: 20px;
      padding: 22px 30px;
      font-weight: 600;
      font-size: 1.2rem;
      color: #0d47a1;
      box-shadow: 0 7px 20px rgba(21, 101, 192, 0.15);
      display: flex;
      align-items: center;
      gap: 16px;
      cursor: default;
      border-left: 8px solid #1976d2;
      transition: background 0.35s ease, color 0.35s ease, border-color 0.35s ease, box-shadow 0.35s ease;
      user-select: none;
    }

    .services li:hover {
      background: #1976d2;
      color: #fff;
      box-shadow: 0 10px 30px rgba(21, 101, 192, 0.4);
      border-left-color: #ffca28;
    }

    /* CONTACT */
    .contact p {
      font-size: 1.35rem;
      margin: 18px 0;
      color: #34495e;
      text-align: center;
      transition: color 0.3s ease;
      line-height: 1.6;
    }

    .contact p strong {
      color: #0d47a1;
      font-weight: 700;
    }

    .contact a {
      color: #1565c0;
      font-weight: 700;
      text-decoration: none;
      transition: color 0.3s ease;
    }

    .contact a:hover, .contact a:focus {
      color: #ffca28;
      outline: none;
    }

    /* REVIEWS */
    .reviews ul {
      list-style: none;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
      padding: 0;
    }

    .reviews li {
      background: #f7f9fc;
      border-radius: 20px;
      padding: 28px 25px;
      box-shadow: 0 7px 20px rgba(21, 101, 192, 0.1);
      display: flex;
      flex-direction: column;
      gap: 18px;
      user-select: none;
      transition: box-shadow 0.3s ease;
    }

    .reviews li:hover {
      box-shadow: 0 12px 40px rgba(21, 101, 192, 0.25);
    }

    .review-stars {
      display: flex;
      gap: 6px;
      user-select: none;
    }

    .review-stars svg {
      width: 22px;
      height: 22px;
      fill: #ffca28;
      filter: drop-shadow(0 0 1px rgba(0,0,0,0.2));
      transition: fill 0.3s ease;
    }

    .review-stars svg.empty {
      fill: #d3d3d3;
    }

    .review-text {
      font-size: 1.05rem;
      color: #2c3e50;
      font-style: italic;
      line-height: 1.6;
    }

    .review-author {
      font-weight: 700;
      font-size: 1.15rem;
      color: #0d47a1;
      text-align: right;
      font-style: normal;
    }

    /* FOOTER */
    footer {
      background: #0d47a1;
      padding: 30px 20px;
      text-align: center;
      color: #fffde7;
      font-weight: 600;
      letter-spacing: 1.5px;
      font-size: 1rem;
      box-shadow: 0 -4px 15px rgba(0,0,0,0.15);
      margin-top: auto;
      user-select: none;
      user-select: none;
    }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      section {
        margin: 40px 20px;
        padding: 40px 30px;
      }
    }

    @media (max-width: 700px) {
      nav {
        flex-direction: column;
        gap: 20px;
      }

      section {
        margin: 35px 15px;
        padding: 35px 25px;
      }

      .services ul,
      .reviews ul {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 400px) {
      header {
        font-size: 2.4rem;
        padding: 25px 15px;
      }

      nav a {
        font-size: 1.1rem;
      }

      .section-title {
        font-size: 2.2rem;
        margin-bottom: 25px;
      }

      .contact p {
        font-size: 1.15rem;
      }
    }
  </style>
</head>
<body>

  <header>
    Decorinex Real Estate Company
  </header>

  <nav>
    <a href="#about">About Us</a>
    <a href="#services">Services</a>
    <a href="#reviews">Reviews</a>
    <a href="#contact">Contact Us</a>
  </nav>

  <section id="about" class="about">
    <h2 class="section-title">About Us</h2>
    <p>
      At <strong>Decorinex</strong>, we redefine real estate with unmatched style and innovation.
      With years of experience, we specialize in premium property sales, rentals, and interior staging.
      Our mission is to help you find your perfect space while delivering top notch customer experience.
    </p>
  </section>

  <section id="services" class="services">
    <h2 class="section-title">Our Services</h2>
    <ul>
      <li>🏠 Property Buying & Selling</li>
      <li>📐 Interior Design & Home Staging</li>
      <li>🏢 Commercial Property Leasing</li>
      <li>🔍 Property Management & Consultancy</li>
      <li>📸 Virtual Tours & Photography</li>
    </ul>
  </section>

  <section id="reviews" class="reviews">
    <h2 class="section-title">What Our Clients Say</h2>
    <ul>
      <li>
        <div class="review-stars" aria-label="5 stars">
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
        </div>
        <p class="review-text">"Decorinex made buying my first home a breeze! Professional, friendly, and attentive throughout the entire process."</p>
        <div class="review-author">— Salim M.</div>
      </li>
      <li>
        <div class="review-stars" aria-label="4 stars">
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg class="empty" viewBox="0 0 24 24" aria-hidden="true"><path d="M22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21 12 17.27 18.18 21l-1.64-7.03L22 9.24z"/></svg>
        </div>
        <p class="review-text">"Great service with excellent attention to detail. The staging helped sell my property quickly."</p>
        <div class="review-author">— Ibrahim T.</div>
      </li>
      <li>
        <div class="review-stars" aria-label="5 stars">
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
        </div>
        <p class="review-text">"Highly recommend for commercial leasing. The team is knowledgeable and very responsive."</p>
        <div class="review-author">— Fahad K.</div>
      </li>
      <li>
        <div class="review-stars" aria-label="4 stars">
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z"/></svg>
          <svg class="empty" viewBox="0 0 24 24" aria-hidden="true"><path d="M22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21 12 17.27 18.18 21l-1.64-7.03L22 9.24z"/></svg>
        </div>
        <p class="review-text">"Virtual tours and photography were top-notch. Helped us attract many interested buyers."</p>
        <div class="review-author">— Robert P.</div>
      </li>
    </ul>
  </section>

  <section id="contact" class="contact">
    <h2 class="section-title">Contact Us</h2>
    <p><strong>Phone:</strong> <a href="tel:+234">+234 9041347678</a></p>
    <p><strong>Email:</strong> <a href="mailto:info@decorinex.com">info@decorinex.com</a></p>
    <p><strong>Address:</strong> No 16. Kofar kaura road Katsina</p>
    <p>We`re available Monday to Saturday, 9am to 6pm. Reach out and let us help you find your dream property!</p>
  </section>

  <footer>
    &copy; 2025 Decorinex Real Estate. All rights reserved.
  </footer>

</body>
</html>
