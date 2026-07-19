<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">

  <meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
  >

  <meta
    name="description"
    content="Jasmine Financial Solutions helps families learn about protection, budgeting, savings, retirement planning, and financial opportunities."
  >

  <title>Jasmine Financial Solutions</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      scroll-behavior: smooth;
    }

    :root {
      --dark-purple: #32102a;
      --purple: #65154f;
      --pink: #bd438c;
      --light-pink: #f7d5e9;
      --soft-pink: #fff6fb;
      --gold: #e7be72;
      --light-gold: #f8e6b8;
      --white: #ffffff;
      --dark-text: #2b2028;
      --gray-text: #6f606a;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: var(--soft-pink);
      color: var(--dark-text);
      line-height: 1.6;
    }

    img {
      max-width: 100%;
    }

    a {
      text-decoration: none;
    }

    button,
    input,
    select,
    textarea {
      font-family: inherit;
    }

    .container {
      width: min(1150px, 92%);
      margin: 0 auto;
    }

    /* NAVIGATION */

    .navbar {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(50, 16, 42, 0.96);
      border-bottom: 1px solid rgba(231, 190, 114, 0.35);
      backdrop-filter: blur(10px);
    }

    .nav-container {
      min-height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 25px;
    }

    .logo {
      color: var(--white);
      font-size: 1.35rem;
      font-weight: 800;
      letter-spacing: 0.5px;
    }

    .logo span {
      color: var(--gold);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 25px;
      list-style: none;
    }

    .nav-links a {
      color: var(--white);
      font-weight: 700;
      transition: 0.25s;
    }

    .nav-links a:hover {
      color: var(--gold);
    }

    .menu-button {
      display: none;
      background: transparent;
      border: 1px solid var(--gold);
      color: var(--white);
      border-radius: 8px;
      padding: 9px 13px;
      cursor: pointer;
      font-size: 1rem;
    }

    /* HERO */

    .hero {
      min-height: 88vh;
      display: flex;
      align-items: center;
      color: var(--white);
      background:
        radial-gradient(
          circle at 75% 25%,
          rgba(222, 105, 170, 0.28),
          transparent 34%
        ),
        linear-gradient(
          135deg,
          #2c0d25 0%,
          #671850 50%,
          #9b3376 100%
        );
      overflow: hidden;
      position: relative;
    }

    .hero::before {
      content: "";
      position: absolute;
      width: 350px;
      height: 350px;
      border: 1px solid rgba(231, 190, 114, 0.18);
      border-radius: 50%;
      top: -120px;
      left: -100px;
    }

    .hero-grid {
      position: relative;
      z-index: 2;
      display: grid;
      grid-template-columns: 1.05fr 0.95fr;
      gap: 55px;
      align-items: center;
      padding: 70px 0;
    }

    .eyebrow {
      display: inline-block;
      color: var(--gold);
      font-size: 0.88rem;
      font-weight: 800;
      letter-spacing: 3px;
      text-transform: uppercase;
      margin-bottom: 17px;
    }

    .hero h1 {
      font-size: clamp(2.8rem, 6vw, 5.4rem);
      line-height: 1.03;
      margin-bottom: 22px;
    }

    .hero h1 span {
      color: var(--light-gold);
    }

    .hero-text {
      max-width: 650px;
      font-size: 1.1rem;
      color: #f7eaf2;
      margin-bottom: 30px;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
    }

    .button {
      display: inline-block;
      border-radius: 999px;
      padding: 14px 24px;
      font-weight: 800;
      transition: 0.25s;
      border: 2px solid transparent;
    }

    .button-primary {
      background: var(--gold);
      color: var(--dark-purple);
    }

    .button-primary:hover {
      background: var(--light-gold);
      transform: translateY(-2px);
    }

    .button-secondary {
      color: var(--white);
      border-color: rgba(255, 255, 255, 0.65);
    }

    .button-secondary:hover {
      background: var(--white);
      color: var(--purple);
    }

    .profile-card {
      background: rgba(255, 255, 255, 0.12);
      border: 1px solid rgba(255, 255, 255, 0.28);
      border-radius: 30px;
      padding: 22px;
      text-align: center;
      backdrop-filter: blur(10px);
      box-shadow: 0 25px 70px rgba(20, 3, 16, 0.32);
    }

    .profile-photo {
      width: 100%;
      max-height: 540px;
      aspect-ratio: 1 / 1;
      object-fit: cover;
      object-position: center;
      border-radius: 22px;
      border: 4px solid rgba(231, 190, 114, 0.82);
      display: block;
    }

    .profile-card h2 {
      font-size: 1.9rem;
      margin-top: 20px;
      color: var(--light-gold);
    }

    .profile-card p {
      color: #f7eaf2;
      margin-top: 4px;
    }

    /* SHARED SECTION STYLES */

    section {
      padding: 90px 0;
    }

    .section-heading {
      max-width: 760px;
      text-align: center;
      margin: 0 auto 50px;
    }

    .section-heading .small-title {
      color: var(--pink);
      font-size: 0.85rem;
      font-weight: 800;
      letter-spacing: 3px;
      text-transform: uppercase;
      margin-bottom: 9px;
    }

    .section-heading h2 {
      color: var(--dark-purple);
      font-size: clamp(2rem, 4vw, 3.2rem);
      line-height: 1.15;
      margin-bottom: 15px;
    }

    .section-heading p {
      color: var(--gray-text);
    }

    /* SERVICES */

    .services {
      background: var(--white);
    }

    .service-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }

    .service-card {
      border: 1px solid #efd7e6;
      border-radius: 22px;
      background: var(--soft-pink);
      padding: 30px;
      transition: 0.25s;
    }

    .service-card:hover {
      transform: translateY(-7px);
      box-shadow: 0 18px 35px rgba(78, 18, 59, 0.12);
      border-color: var(--gold);
    }

    .service-icon {
      width: 58px;
      height: 58px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: var(--light-pink);
      font-size: 1.8rem;
      margin-bottom: 18px;
    }

    .service-card h3 {
      color: var(--purple);
      font-size: 1.28rem;
      margin-bottom: 10px;
    }

    .service-card p {
      color: var(--gray-text);
    }

    /* ABOUT */

    .about {
      background:
        linear-gradient(
          135deg,
          #fff7fb 0%,
          #f8dfed 100%
        );
    }

    .about-grid {
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      gap: 55px;
      align-items: center;
    }

    .about-image-box {
      background: linear-gradient(145deg, var(--purple), var(--pink));
      padding: 24px;
      border-radius: 28px;
      box-shadow: 0 24px 55px rgba(87, 20, 66, 0.18);
    }

    .about-image-box img {
      width: 100%;
      border-radius: 19px;
      display: block;
    }

    .about-content .small-title {
      color: var(--pink);
      font-size: 0.85rem;
      font-weight: 800;
      letter-spacing: 3px;
      text-transform: uppercase;
      margin-bottom: 10px;
    }

    .about-content h2 {
      font-size: clamp(2rem, 4vw, 3.1rem);
      color: var(--dark-purple);
      line-height: 1.15;
      margin-bottom: 20px;
    }

    .about-content p {
      color: var(--gray-text);
      margin-bottom: 17px;
    }

    .about-list {
      margin-top: 25px;
      display: grid;
      gap: 13px;
    }

    .about-list div {
      display: flex;
      align-items: center;
      gap: 12px;
      font-weight: 700;
      color: var(--purple);
    }

    .check {
      width: 28px;
      height: 28px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: var(--gold);
      color: var(--dark-purple);
      flex-shrink: 0;
    }

    /* PROCESS */

    .process {
      background: var(--white);
    }

    .step-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
    }

    .step {
      text-align: center;
      padding: 30px 22px;
    }

    .step-number {
      width: 72px;
      height: 72px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--purple), var(--pink));
      color: var(--white);
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 20px;
      font-size: 1.45rem;
      font-weight: 800;
      border: 5px solid var(--light-pink);
    }

    .step h3 {
      color: var(--purple);
      margin-bottom: 10px;
      font-size: 1.3rem;
    }

    .step p {
      color: var(--gray-text);
    }

    /* QUOTE */

    .quote-section {
      padding: 75px 0;
      color: var(--white);
      text-align: center;
      background:
        linear-gradient(
          rgba(49, 15, 41, 0.93),
          rgba(49, 15, 41, 0.93)
        ),
        linear-gradient(135deg, var(--purple), var(--pink));
    }

    .quote-section blockquote {
      max-width: 900px;
      margin: 0 auto;
      font-family: Georgia, "Times New Roman", serif;
      font-size: clamp(1.8rem, 4vw, 3rem);
      line-height: 1.3;
      color: var(--light-gold);
    }

    .quote-section p {
      margin-top: 20px;
      color: #f6deeb;
      font-weight: 700;
      letter-spacing: 1px;
    }

    /* CONTACT */

    .contact {
      background: var(--soft-pink);
    }

    .contact-grid {
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      gap: 50px;
      align-items: start;
    }

    .contact-info {
      background: linear-gradient(145deg, var(--dark-purple), var(--purple));
      color: var(--white);
      border-radius: 26px;
      padding: 38px;
    }

    .contact-info h2 {
      font-size: 2.4rem;
      line-height: 1.2;
      margin-bottom: 18px;
      color: var(--light-gold);
    }

    .contact-info p {
      color: #f3dce9;
      margin-bottom: 20px;
    }

    .contact-detail {
      display: flex;
      align-items: center;
      gap: 13px;
      margin-top: 17px;
    }

    .contact-detail span:first-child {
      width: 40px;
      height: 40px;
      background: rgba(231, 190, 114, 0.17);
      border: 1px solid rgba(231, 190, 114, 0.45);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .contact-form {
      background: var(--white);
      border: 1px solid #efd7e6;
      border-radius: 26px;
      padding: 34px;
      box-shadow: 0 16px 38px rgba(74, 17, 56, 0.1);
    }

    .form-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
    }

    .form-group {
      margin-bottom: 18px;
    }

    .form-group label {
      display: block;
      color: var(--purple);
      font-weight: 800;
      margin-bottom: 7px;
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%;
      border: 1px solid #dbc1d1;
      border-radius: 11px;
      padding: 13px;
      font-size: 1rem;
      background: #fffafd;
      outline: none;
    }

    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
      border-color: var(--pink);
      box-shadow: 0 0 0 3px rgba(189, 67, 140, 0.12);
    }

    .form-group textarea {
      min-height: 125px;
      resize: vertical;
    }

    .submit-button {
      width: 100%;
      border: none;
      border-radius: 999px;
      padding: 15px 22px;
      background: linear-gradient(135deg, var(--purple), var(--pink));
      color: var(--white);
      font-size: 1rem;
      font-weight: 800;
      cursor: pointer;
      transition: 0.25s;
    }

    .submit-button:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 24px rgba(106, 25, 81, 0.22);
    }

    .success-message {
      display: none;
      margin-top: 15px;
      border-radius: 10px;
      padding: 12px;
      background: #f7e6b8;
      color: #50360c;
      font-weight: 700;
      text-align: center;
    }

    /* DISCLAIMER AND FOOTER */

    .disclaimer {
      background: #25101f;
      color: #d8c4d0;
      text-align: center;
      font-size: 0.83rem;
      padding: 25px 15px;
    }

    footer {
      background: #160913;
      color: var(--white);
      text-align: center;
      padding: 22px 15px;
    }

    footer span {
      color: var(--gold);
    }

    /* MOBILE */

    @media (max-width: 900px) {
      .nav-links {
        position: absolute;
        top: 76px;
        left: 0;
        width: 100%;
        display: none;
        flex-direction: column;
        align-items: flex-start;
        background: var(--dark-purple);
        padding: 24px 5%;
        border-top: 1px solid rgba(231, 190, 114, 0.3);
      }

      .nav-links.show {
        display: flex;
      }

      .menu-button {
        display: block;
      }

      .hero-grid,
      .about-grid,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .hero {
        text-align: center;
      }

      .hero-text {
        margin-left: auto;
        margin-right: auto;
      }

      .hero-buttons {
        justify-content: center;
      }

      .profile-card {
        max-width: 600px;
        margin: 0 auto;
      }

      .service-grid,
      .step-grid {
        grid-template-columns: 1fr 1fr;
      }

      .about-image-box {
        max-width: 620px;
        margin: 0 auto;
      }
    }

    @media (max-width: 620px) {
      section {
        padding: 70px 0;
      }

      .logo {
        font-size: 1.05rem;
      }

      .hero-grid {
        padding: 55px 0;
      }

      .hero h1 {
        font-size: 2.65rem;
      }

      .service-grid,
      .step-grid,
      .form-row {
        grid-template-columns: 1fr;
      }

      .contact-info,
      .contact-form {
        padding: 27px 22px;
      }

      .profile-card {
        padding: 15px;
      }
    }
  </style>
</head>

<body>

  <!-- NAVIGATION -->

  <nav class="navbar">
    <div class="container nav-container">

      <a href="#home" class="logo">
        Jasmine <span>Financial Solutions</span>
      </a>

      <button
        class="menu-button"
        id="menuButton"
        type="button"
        aria-label="Open navigation menu"
      >
        Menu
      </button>

      <ul class="nav-links" id="navLinks">
        <li><a href="#home">Home</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#about">About Jasmine</a></li>
        <li><a href="#process">Getting Started</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>

    </div>
  </nav>


  <!-- HERO SECTION -->

  <header class="hero" id="home">
    <div class="container hero-grid">

      <div>
        <span class="eyebrow">
          Confident • Focused • Unstoppable
        </span>

        <h1>
          Helping families build a
          <span>stronger financial future.</span>
        </h1>

        <p class="hero-text">
          Jasmine helps individuals and families better understand financial
          protection, budgeting, savings, retirement planning, and business
          opportunities through personal financial education.
        </p>

        <div class="hero-buttons">
          <a href="#contact" class="button button-primary">
            Schedule a Free Consultation
          </a>

          <a href="#services" class="button button-secondary">
            Explore Services
          </a>
        </div>
      </div>

      <div class="profile-card">

        <img
          src="jasmine-professional.png"
          alt="Jasmine, financial services representative"
          class="profile-photo"
        >

        <h2>Meet Jasmine</h2>

        <p>
          Independent Financial Services Representative
        </p>

      </div>

    </div>
  </header>


  <!-- SERVICES SECTION -->

  <section class="services" id="services">
    <div class="container">

      <div class="section-heading">
        <p class="small-title">How Jasmine Can Help</p>

        <h2>
          Financial information made easier to understand
        </h2>

        <p>
          Begin with a personal conversation about your family's needs,
          priorities, and long-term goals.
        </p>
      </div>

      <div class="service-grid">

        <article class="service-card">
          <div class="service-icon">🛡️</div>

          <h3>Life Insurance Education</h3>

          <p>
            Learn how financial protection may help your family prepare for
            future responsibilities and unexpected life events.
          </p>
        </article>

        <article class="service-card">
          <div class="service-icon">💰</div>

          <h3>Budgeting Guidance</h3>

          <p>
            Review your monthly expenses and create a clearer plan for your
            money, savings, and financial priorities.
          </p>
        </article>

        <article class="service-card">
          <div class="service-icon">📈</div>

          <h3>Retirement Planning</h3>

          <p>
            Explore financial concepts and options designed to support your
            long-term retirement goals.
          </p>
        </article>

        <article class="service-card">
          <div class="service-icon">🎓</div>

          <h3>College Savings</h3>

          <p>
            Discuss ways to begin preparing for future education expenses and
            important family milestones.
          </p>
        </article>

        <article class="service-card">
          <div class="service-icon">👨‍👩‍👧‍👦</div>

          <h3>Family Financial Review</h3>

          <p>
            Receive a personal review centered on your current situation,
            concerns, and financial goals.
          </p>
        </article>

        <article class="service-card">
          <div class="service-icon">💼</div>

          <h3>Business Opportunity</h3>

          <p>
            Learn about the opportunity to build a part-time or full-time
            financial services business.
          </p>
        </article>

      </div>
    </div>
  </section>


  <!-- ABOUT SECTION -->

  <section class="about" id="about">
    <div class="container about-grid">

      <div class="about-image-box">

        <img
          src="jasmine-professional.png"
          alt="Jasmine working in a professional financial services office"
        >

      </div>

      <div class="about-content">

        <p class="small-title">About Jasmine</p>

        <h2>
          Financial education with confidence and a personal touch
        </h2>

        <p>
          Jasmine believes families deserve access to financial information
          that feels understandable, practical, and connected to their real
          lives.
        </p>

        <p>
          Her goal is to listen carefully, explain available options, and help
          each person make informed financial decisions based on their own
          needs and priorities.
        </p>

        <p>
          Whether you are thinking about protecting your household, planning
          for the future, organizing your finances, or exploring a new career
          opportunity, Jasmine provides a welcoming place to begin.
        </p>

        <div class="about-list">

          <div>
            <span class="check">✓</span>
            Personal and welcoming conversations
          </div>

          <div>
            <span class="check">✓</span>
            Clear financial education
          </div>

          <div>
            <span class="check">✓</span>
            Family-focused planning
          </div>

          <div>
            <span class="check">✓</span>
            Flexible virtual or in-person meetings
          </div>

        </div>

      </div>

    </div>
  </section>


  <!-- PROCESS SECTION -->

  <section class="process" id="process">
    <div class="container">

      <div class="section-heading">

        <p class="small-title">Getting Started</p>

        <h2>Three simple steps</h2>

        <p>
          Begin your financial conversation without pressure or confusion.
        </p>

      </div>

      <div class="step-grid">

        <div class="step">

          <div class="step-number">1</div>

          <h3>Schedule a Meeting</h3>

          <p>
            Choose a convenient time to meet with Jasmine by telephone,
            virtually, or in person.
          </p>

        </div>

        <div class="step">

          <div class="step-number">2</div>

          <h3>Discuss Your Goals</h3>

          <p>
            Talk openly about your family, finances, concerns, priorities,
            and future plans.
          </p>

        </div>

        <div class="step">

          <div class="step-number">3</div>

          <h3>Review Your Options</h3>

          <p>
            Receive information that can help you understand your choices and
            make informed decisions.
          </p>

        </div>

      </div>

    </div>
  </section>


  <!-- QUOTE SECTION -->

  <section class="quote-section">

    <div class="container">

      <blockquote>
        “I am not lucky—I am focused. I do not chase opportunities;
        I build confidence, discipline, and momentum.”
      </blockquote>

      <p>Jasmine Boss Mode</p>

    </div>

  </section>


  <!-- CONTACT SECTION -->

  <section class="contact" id="contact">
    <div class="container contact-grid">

      <div class="contact-info">

        <h2>
          Start your financial conversation
        </h2>

        <p>
          Complete the form to request a free consultation with Jasmine.
          Meetings may be available virtually, by telephone, or in person.
        </p>

        <div class="contact-detail">
          <span>📞</span>

          <div>
            <strong>Telephone Consultation</strong>
            <br>
            Available by appointment
          </div>
        </div>

        <div class="contact-detail">
          <span>💻</span>

          <div>
            <strong>Virtual Meeting</strong>
            <br>
            Meet from the comfort of your home
          </div>
        </div>

        <div class="contact-detail">
          <span>🤝</span>

          <div>
            <strong>Personal Service</strong>
            <br>
            A conversation focused on your goals
          </div>
        </div>

      </div>

      <div class="contact-form">

        <form id="consultationForm">

          <div class="form-row">

            <div class="form-group">
              <label for="firstName">First Name</label>

              <input
                type="text"
                id="firstName"
                name="firstName"
                placeholder="Enter your first name"
                required
              >
            </div>

            <div class="form-group">
              <label for="lastName">Last Name</label>

              <input
                type="text"
                id="lastName"
                name="lastName"
                placeholder="Enter your last name"
                required
              >
            </div>

          </div>

          <div class="form-row">

            <div class="form-group">
              <label for="phone">Phone Number</label>

              <input
                type="tel"
                id="phone"
                name="phone"
                placeholder="Enter your phone number"
                required
              >
            </div>

            <div class="form-group">
              <label for="email">Email Address</label>

              <input
                type="email"
                id="email"
                name="email"
                placeholder="Enter your email address"
                required
              >
            </div>

          </div>

          <div class="form-group">

            <label for="interest">
              What are you interested in?
            </label>

            <select id="interest" name="interest" required>
              <option value="">Choose an option</option>
              <option>Life Insurance Information</option>
              <option>Budgeting and Financial Planning</option>
              <option>Retirement Planning</option>
              <option>College Savings</option>
              <option>Family Financial Review</option>
              <option>Business Opportunity</option>
            </select>

          </div>

          <div class="form-group">

            <label for="message">Message</label>

            <textarea
              id="message"
              name="message"
              placeholder="Tell Jasmine how she can help"
            ></textarea>

          </div>

          <button type="submit" class="submit-button">
            Request My Free Consultation
          </button>

          <div class="success-message" id="successMessage">
            Thank you! Your request has been received.
          </div>

        </form>

      </div>

    </div>
  </section>


  <!-- DISCLAIMER -->

  <div class="disclaimer">
    This website provides general educational information and does not offer
    legal, tax, or individualized investment advice. Financial products and
    services may require appropriate licensing and company approval. Replace
    this statement with Jasmine's official company, licensing, and compliance
    disclosures before publicly advertising financial products or services.
  </div>


  <!-- FOOTER -->

  <footer>

    <p>
      © <span id="currentYear"></span>
      <span>Jasmine Financial Solutions</span>.
      All rights reserved.
    </p>

  </footer>


  <script>
    const menuButton = document.getElementById("menuButton");
    const navLinks = document.getElementById("navLinks");
    const navigationLinks = document.querySelectorAll(".nav-links a");

    menuButton.addEventListener("click", function () {
      navLinks.classList.toggle("show");
    });

    navigationLinks.forEach(function (link) {
      link.addEventListener("click", function () {
        navLinks.classList.remove("show");
      });
    });


    const consultationForm =
      document.getElementById("consultationForm");

    const successMessage =
      document.getElementById("successMessage");

    consultationForm.addEventListener("submit", function (event) {
      event.preventDefault();

      const firstName =
        document.getElementById("firstName").value.trim();

      successMessage.textContent =
        "Thank you, " +
        firstName +
        "! Your consultation request has been received.";

      successMessage.style.display = "block";

      consultationForm.reset();
    });


    document.getElementById("currentYear").textContent =
      new Date().getFullYear();
  </script>

</body>
</html>
