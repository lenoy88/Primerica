<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Jasmine Financial Solutions</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: #fff8fc;
      color: #29232a;
      line-height: 1.6;
    }

    header {
      background:
        linear-gradient(rgba(68, 12, 51, 0.82), rgba(68, 12, 51, 0.82)),
        linear-gradient(135deg, #8d2d6f, #d88abf);

      color: white;
      min-height: 90vh;
      display: flex;
      flex-direction: column;
    }

    nav {
      width: 100%;
      max-width: 1200px;
      margin: auto;
      margin-top: 0;
      margin-bottom: 0;
      padding: 22px 25px;

      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.55rem;
      font-weight: bold;
      letter-spacing: 1px;
    }

    .nav-links {
      display: flex;
      list-style: none;
      gap: 22px;
    }

    .nav-links a {
      color: white;
      text-decoration: none;
      font-weight: bold;
    }

    .nav-links a:hover {
      color: #ffd7ee;
    }

    .hero {
      max-width: 1200px;
      width: 100%;
      margin: auto;
      padding: 60px 25px 90px;

      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 50px;
      align-items: center;
    }

    .hero-text h1 {
      font-size: clamp(2.7rem, 6vw, 5rem);
      line-height: 1.05;
      margin-bottom: 22px;
    }

    .hero-text h1 span {
      color: #ffd1ea;
    }

    .hero-text p {
      font-size: 1.2rem;
      max-width: 650px;
      margin-bottom: 30px;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
    }

    .button {
      display: inline-block;
      padding: 14px 24px;
      border-radius: 30px;
      text-decoration: none;
      font-weight: bold;
      border: 2px solid white;
      transition: 0.25s;
    }

    .button-primary {
      background: white;
      color: #6d2356;
    }

    .button-primary:hover {
      background: #ffd7ee;
      transform: translateY(-2px);
    }

    .button-secondary {
      color: white;
      background: transparent;
    }

    .button-secondary:hover {
      background: white;
      color: #6d2356;
    }

    .profile-card {
      background: rgba(255, 255, 255, 0.14);
      border: 1px solid rgba(255, 255, 255, 0.35);
      border-radius: 30px;
      padding: 35px;
      text-align: center;
      backdrop-filter: blur(8px);
    }

    .profile-circle {
      width: 210px;
      height: 210px;
      border-radius: 50%;
      margin: 0 auto 22px;

      display: flex;
      align-items: center;
      justify-content: center;

      background: linear-gradient(135deg, #ffd2ea, #ffffff);
      color: #6d2356;
      border: 7px solid rgba(255, 255, 255, 0.85);

      font-size: 5rem;
      font-weight: bold;
    }

    .profile-card h2 {
      font-size: 2rem;
      margin-bottom: 8px;
    }

    .profile-card p {
      color: #ffeaf6;
    }

    section {
      padding: 85px 25px;
    }

    .container {
      width: 100%;
      max-width: 1150px;
      margin: auto;
    }

    .section-heading {
      text-align: center;
      margin-bottom: 50px;
    }

    .section-heading p {
      color: #8d2d6f;
      font-weight: bold;
      text-transform: uppercase;
      letter-spacing: 2px;
      margin-bottom: 8px;
    }

    .section-heading h2 {
      font-size: clamp(2rem, 4vw, 3rem);
      color: #3e1733;
    }

    .services {
      background: white;
    }

    .service-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
    }

    .service-card {
      background: #fff8fc;
      border: 1px solid #f1d5e7;
      border-radius: 20px;
      padding: 32px;
      box-shadow: 0 10px 25px rgba(91, 24, 70, 0.08);
      transition: 0.25s;
    }

    .service-card:hover {
      transform: translateY(-7px);
      box-shadow: 0 16px 35px rgba(91, 24, 70, 0.14);
    }

    .service-icon {
      font-size: 2.3rem;
      margin-bottom: 17px;
    }

    .service-card h3 {
      color: #6d2356;
      margin-bottom: 10px;
      font-size: 1.35rem;
    }

    .about {
      background: #f8e9f2;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      gap: 50px;
      align-items: center;
    }

    .about-box {
      background: linear-gradient(135deg, #6d2356, #b34c8f);
      color: white;
      border-radius: 25px;
      padding: 45px 35px;
      text-align: center;
    }

    .about-box .large-number {
      font-size: 4.5rem;
      font-weight: bold;
      line-height: 1;
      color: #ffd7ee;
    }

    .about-text h2 {
      font-size: 2.5rem;
      color: #3e1733;
      margin-bottom: 20px;
    }

    .about-text p {
      margin-bottom: 16px;
    }

    .steps {
      background: white;
    }

    .step-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
    }

    .step {
      text-align: center;
      padding: 20px;
    }

    .step-number {
      width: 65px;
      height: 65px;
      border-radius: 50%;
      margin: 0 auto 18px;

      background: #6d2356;
      color: white;

      display: flex;
      align-items: center;
      justify-content: center;

      font-size: 1.5rem;
      font-weight: bold;
    }

    .step h3 {
      color: #6d2356;
      margin-bottom: 10px;
    }

    .contact {
      background: linear-gradient(135deg, #3e1733, #7b285f);
      color: white;
    }

    .contact-wrapper {
      display: grid;
      grid-template-columns: 0.8fr 1.2fr;
      gap: 45px;
      align-items: start;
    }

    .contact-info h2 {
      font-size: 2.6rem;
      margin-bottom: 18px;
    }

    .contact-info p {
      color: #f6ddeb;
      margin-bottom: 15px;
    }

    form {
      background: white;
      padding: 32px;
      border-radius: 22px;
      color: #29232a;
    }

    label {
      display: block;
      font-weight: bold;
      margin-top: 15px;
      margin-bottom: 6px;
      color: #5a2348;
    }

    input,
    select,
    textarea {
      width: 100%;
      padding: 13px;
      border: 1px solid #d9bfd0;
      border-radius: 10px;
      font-size: 1rem;
      font-family: inherit;
    }

    textarea {
      min-height: 120px;
      resize: vertical;
    }

    form button {
      width: 100%;
      margin-top: 20px;
      padding: 15px;
      border: none;
      border-radius: 30px;
      background: #6d2356;
      color: white;
      font-size: 1rem;
      font-weight: bold;
      cursor: pointer;
    }

    form button:hover {
      background: #942f73;
    }

    .disclaimer {
      background: #281020;
      color: #d7becf;
      padding: 28px 25px;
      font-size: 0.83rem;
      text-align: center;
    }

    footer {
      background: #190a14;
      color: white;
      text-align: center;
      padding: 22px;
    }

    @media (max-width: 850px) {
      .hero,
      .about-grid,
      .contact-wrapper {
        grid-template-columns: 1fr;
      }

      .hero {
        text-align: center;
      }

      .hero-text p {
        margin-left: auto;
        margin-right: auto;
      }

      .hero-buttons {
        justify-content: center;
      }

      .service-grid,
      .step-grid {
        grid-template-columns: 1fr;
      }

      .nav-links {
        display: none;
      }

      header {
        min-height: auto;
      }
    }
  </style>
</head>

<body>

  <header id="home">
    <nav>
      <div class="logo">Jasmine Financial Solutions</div>

      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#about">About Jasmine</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>

    <div class="hero">
      <div class="hero-text">
        <h1>
          Helping families build a
          <span>stronger financial future.</span>
        </h1>

        <p>
          Jasmine helps individuals and families better understand life
          insurance, saving, budgeting, and long-term financial planning.
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
        <!-- Replace this circle with Jasmine's photo later -->
        <div class="profile-circle">J</div>

        <h2>Meet Jasmine</h2>

        <p>
          Independent Financial Services Representative
        </p>
      </div>
    </div>
  </header>


  <section class="services" id="services">
    <div class="container">

      <div class="section-heading">
        <p>How Jasmine Can Help</p>
        <h2>Financial guidance made easier to understand</h2>
      </div>

      <div class="service-grid">

        <div class="service-card">
          <div class="service-icon">🛡️</div>

          <h3>Life Insurance Education</h3>

          <p>
            Learn how term life insurance may help protect your family's
            income and future financial responsibilities.
          </p>
        </div>

        <div class="service-card">
          <div class="service-icon">💰</div>

          <h3>Budgeting Guidance</h3>

          <p>
            Review your current expenses, financial goals, and opportunities
            to create a more organized monthly plan.
          </p>
        </div>

        <div class="service-card">
          <div class="service-icon">📈</div>

          <h3>Retirement Planning</h3>

          <p>
            Explore financial concepts and available options that may help
            you prepare for long-term retirement goals.
          </p>
        </div>

        <div class="service-card">
          <div class="service-icon">🎓</div>

          <h3>College Savings</h3>

          <p>
            Discuss ways families can begin planning ahead for future
            education expenses.
          </p>
        </div>

        <div class="service-card">
          <div class="service-icon">👨‍👩‍👧‍👦</div>

          <h3>Family Financial Review</h3>

          <p>
            Receive a personal review focused on your family's priorities,
            concerns, and future financial goals.
          </p>
        </div>

        <div class="service-card">
          <div class="service-icon">💼</div>

          <h3>Business Opportunity</h3>

          <p>
            Learn about building a part-time or full-time career as an
            independent financial services representative.
          </p>
        </div>

      </div>
    </div>
  </section>


  <section class="about" id="about">
    <div class="container about-grid">

      <div class="about-box">
        <div class="large-number">1</div>

        <h3>Family at a Time</h3>

        <p>
          Jasmine's goal is to help people feel more confident when making
          important financial decisions.
        </p>
      </div>

      <div class="about-text">
        <h2>Financial education with a personal touch</h2>

        <p>
          Jasmine believes that financial information should not feel
          confusing or intimidating. Her approach is centered on listening,
          educating, and helping families understand their options.
        </p>

        <p>
          Whether someone is concerned about protecting their household,
          saving for the future, or exploring a new business opportunity,
          Jasmine provides a welcoming place to start the conversation.
        </p>
      </div>

    </div>
  </section>


  <section class="steps">
    <div class="container">

      <div class="section-heading">
        <p>Getting Started</p>
        <h2>Three simple steps</h2>
      </div>

      <div class="step-grid">

        <div class="step">
          <div class="step-number">1</div>

          <h3>Schedule a Meeting</h3>

          <p>
            Choose a convenient time to speak with Jasmine.
          </p>
        </div>

        <div class="step">
          <div class="step-number">2</div>

          <h3>Discuss Your Goals</h3>

          <p>
            Talk about your family, finances, needs, and future plans.
          </p>
        </div>

        <div class="step">
          <div class="step-number">3</div>

          <h3>Review Your Options</h3>

          <p>
            Receive information designed to help you make an informed decision.
          </p>
        </div>

      </div>
    </div>
  </section>


  <section class="contact" id="contact">
    <div class="container contact-wrapper">

      <div class="contact-info">
        <h2>Start your financial conversation</h2>

        <p>
          Complete the form to request a free financial consultation with
          Jasmine.
        </p>

        <p>
          Meetings may be available virtually, by telephone, or in person.
        </p>
      </div>

      <form id="consultationForm">

        <label for="name">Full Name</label>
        <input
          type="text"
          id="name"
          placeholder="Enter your full name"
          required
        />

        <label for="phone">Phone Number</label>
        <input
          type="tel"
          id="phone"
          placeholder="Enter your phone number"
          required
        />

        <label for="email">Email Address</label>
        <input
          type="email"
          id="email"
          placeholder="Enter your email address"
          required
        />

        <label for="interest">What are you interested in?</label>
        <select id="interest" required>
          <option value="">Choose an option</option>
          <option>Life Insurance Information</option>
          <option>Budgeting and Financial Planning</option>
          <option>Retirement Planning</option>
          <option>College Savings</option>
          <option>Business Opportunity</option>
        </select>

        <label for="message">Message</label>
        <textarea
          id="message"
          placeholder="Tell Jasmine how she can help"
        ></textarea>

        <button type="submit">
          Request My Consultation
        </button>

      </form>
    </div>
  </section>


  <div class="disclaimer">
    This website is for general educational and informational purposes only.
    Financial products and services may require appropriate licensing and
    approval. Replace this statement with Jasmine's official company,
    licensing, compliance, and disclosure language before publishing.
  </div>


  <footer>
    <p>
      © 2026 Jasmine Financial Solutions. All rights reserved.
    </p>
  </footer>


  <script>
    const consultationForm = document.getElementById("consultationForm");

    consultationForm.addEventListener("submit", function(event) {
      event.preventDefault();

      const customerName = document.getElementById("name").value;

      alert(
        "Thank you, " +
        customerName +
        "! Your consultation request has been received."
      );

      consultationForm.reset();
    });
  </script>

</body>
</html>
