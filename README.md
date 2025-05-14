<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Track Mate - AI Bot for Order Management & Delivery Prediction</title>
<style>
  /* Reset & base */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: #f9fbfd;
    color: #212121;
    line-height: 1.6;
  }
  a {
    text-decoration: none;
    color: #0f62fe;
  }
  a:hover {
    color: #0043ce;
  }
  img {
    max-width: 100%;
    height: auto;
    display: block;
  }

  /* Container */
  .container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 24px;
  }

  /* Header */
  header {
    background: #0f62fe;
    color: white;
    padding: 20px 0;
    position: sticky;
    top: 0;
    z-index: 100;
  }
  header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  header h1 {
    font-weight: 700;
    font-size: 1.8rem;
  }
  nav ul {
    list-style: none;
    display: flex;
    gap: 22px;
  }
  nav ul li a {
    color: white;
    font-weight: 600;
    font-size: 1rem;
    padding: 8px 12px;
    border-radius: 4px;
    transition: background-color 0.3s ease;
  }
  nav ul li a:hover,
  nav ul li a:focus {
    background: #0043ce;
  }

  /* Hero Section */
  .hero {
    background: linear-gradient(135deg, #0f62fe 0%, #005aff 90%);
    color: white;
    padding: 100px 24px 80px;
    text-align: center;
  }
  .hero h2 {
    font-size: 2.7rem;
    font-weight: 900;
    margin-bottom: 20px;
    line-height: 1.1;
  }
  .hero p {
    font-size: 1.25rem;
    margin-bottom: 40px;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
    font-weight: 500;
  }
  .btn-primary {
    background-color: #ffe600;
    color: #212121;
    font-weight: 700;
    font-size: 1.2rem;
    border: none;
    padding: 14px 30px;
    border-radius: 50px;
    cursor: pointer;
    transition: background-color 0.3s ease;
    box-shadow: 0 5px 15px rgba(255, 230, 0, 0.6);
  }
  .btn-primary:hover,
  .btn-primary:focus {
    background-color: #ffb800;
  }

  /* Section Titles */
  section h3 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 40px;
    color: #0f62fe;
    font-weight: 700;
  }

  /* Features Grid */
  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(280px,1fr));
    gap: 30px;
    margin-bottom: 80px;
  }
  .feature-card {
    background: white;
    border-radius: 12px;
    box-shadow: 0 10px 25px rgba(15, 98, 254, 0.1);
    padding: 25px 20px;
    transition: transform 0.3s ease;
  }
  .feature-card:hover {
    transform: translateY(-8px);
  }
  .feature-icon {
    background: #e0e6ff;
    width: 60px;
    height: 60px;
    border-radius: 50%;
    margin-bottom: 18px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #0f62fe;
    font-size: 30px;
  }
  .feature-card h4 {
    font-weight: 700;
    margin-bottom: 12px;
    font-size: 1.2rem;
  }
  .feature-card p {
    color: #616161;
    font-size: 0.95rem;
  }

  /* How It Works - Flow Container */
  .flow-container {
    max-width: 900px;
    margin: 0 auto 80px;
    padding: 0 12px;
  }
  .step {
    background: white;
    border-radius: 12px;
    box-shadow: 0 10px 25px rgba(15, 98, 254, 0.1);
    margin-bottom: 24px;
    padding: 20px 25px;
    display: flex;
    gap: 20px;
    align-items: center;
  }
  .step-icon {
    background: #0f62fe;
    color: white;
    border-radius: 50%;
    width: 48px;
    height: 48px;
    font-weight: 700;
    font-size: 1.25rem;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }
  .step-content h5 {
    font-weight: 700;
    color: #0f62fe;
    margin-bottom: 6px;
  }
  .step-content p {
    font-size: 1rem;
    color: #444;
  }

  /* Testimonials */
  .testimonials {
    background: #eef3ff;
    padding: 60px 24px;
  }
  .testimonials h3 {
    margin-bottom: 50px;
  }
  .testimonial-cards {
    display: grid;
    gap: 32px;
    grid-template-columns: repeat(auto-fit,minmax(300px,1fr));
    max-width: 1100px;
    margin: 0 auto;
  }
  .testimonial-card {
    background: white;
    box-shadow: 0 5px 18px rgba(0,0,0,0.07);
    border-radius: 12px;
    padding: 24px;
    font-style: italic;
    position: relative;
  }
  .testimonial-card::before {
    content: '“';
    font-size: 3rem;
    position: absolute;
    top: 8px;
    left: 14px;
    color: #0f62fe;
  }
  .testimonial-author {
    margin-top: 16px;
    font-weight: 700;
    font-style: normal;
    color: #0f62fe;
    text-align: right;
  }

  /* Pricing Section */
  .pricing-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 30px;
    max-width: 1100px;
    margin: 0 auto 80px;
  }
  .pricing-card {
    background: white;
    box-shadow: 0 10px 25px rgba(15, 98, 254, 0.12);
    border-radius: 12px;
    width: 320px;
    padding: 24px 30px;
    text-align: center;
    transition: transform 0.3s ease;
  }
  .pricing-card.popular {
    border: 3px solid #0f62fe;
    transform: scale(1.05);
  }
  .pricing-card h4 {
    color: #0f62fe;
    font-weight: 900;
    font-size: 1.6rem;
    margin-bottom: 15px;
  }
  .pricing-card .price {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 25px;
    color: #333;
  }
  .pricing-card ul {
    list-style: none;
    margin-bottom: 30px;
  }
  .pricing-card ul li {
    font-size: 1rem;
    margin-bottom: 14px;
    color: #555;
  }
  .pricing-card ul li::before {
    content: '✓';
    color: #0f62fe;
    margin-right: 8px;
    font-weight: bold;
  }
  .pricing-card button {
    background-color: #0f62fe;
    color: white;
    font-weight: 700;
    border: none;
    padding: 14px 0;
    border-radius: 50px;
    width: 100%;
    cursor: pointer;
    font-size: 1.1rem;
    box-shadow: 0 5px 15px rgba(15, 98, 254, 0.5);
    transition: background-color 0.3s ease;
  }
  .pricing-card button:hover {
    background-color: #0043ce;
  }

  /* Blog & Resources Section */
  .blog-section {
    max-width: 1100px;
    margin: 0 auto 80px;
  }
  .blog-posts {
    display: grid;
    gap: 24px;
    grid-template-columns: repeat(auto-fit,minmax(280px,1fr));
  }
  .blog-post {
    background: white;
    border-radius: 12px;
    box-shadow: 0 10px 25px rgba(15, 98, 254, 0.1);
    padding: 24px 26px;
    transition: transform 0.3s ease;
  }
  .blog-post:hover {
    transform: translateY(-6px);
  }
  .blog-post h5 {
    margin-bottom: 12px;
    color: #0f62fe;
    font-weight: 700;
    font-size: 1.1rem;
  }
  .blog-post p {
    font-size: 0.95rem;
    line-height: 1.4;
    color: #444;
  }
  .blog-post a {
    display: inline-block;
    margin-top: 16px;
    font-weight: 700;
    font-size: 0.95rem;
    color: #0f62fe;
  }
  .blog-post a:hover {
    color: #0043ce;
  }

  /* Contact Section */
  .contact-section {
    background: #0f62fe;
    color: white;
    padding: 60px 24px;
  }
  .contact-section h3 {
    margin-bottom: 30px;
  }
  form {
    max-width: 500px;
    margin: 0 auto;
  }
  label {
    display: block;
    margin-bottom: 8px;
    font-weight: 700;
  }
  input, textarea {
    width: 100%;
    padding: 12px 14px;
    margin-bottom: 20px;
    border-radius: 8px;
    border: none;
    font-size: 1rem;
  }
  textarea {
    resize: vertical;
    min-height: 120px;
  }
  button[type="submit"] {
    background-color: #ffe600;
    color: #212121;
    font-weight: 700;
    border: none;
    padding: 14px 28px;
    border-radius: 50px;
    cursor: pointer;
    width: 100%;
    font-size: 1.2rem;
    transition: background-color 0.3s ease;
    box-shadow: 0 5px 15px rgba(255, 230, 0, 0.7);
  }
  button[type="submit"]:hover {
    background-color: #ffb800;
  }

  /* Footer */
  footer {
    background: #212121;
    color: #cfcfcf;
    font-size: 0.85rem;
    text-align: center;
    padding: 18px 24px;
  }
  footer a {
    color: #ffe600;
  }
  footer a:hover {
    color: #ffb800;
  }

  /* Responsive tweaks */
  @media (max-width: 600px) {
    header .container {
      flex-direction: column;
      gap: 12px;
    }
    nav ul {
      flex-direction: column;
      align-items: center;
      gap: 14px;
    }
    .pricing-cards {
      flex-direction: column;
      width: 100%;
      align-items: center;
    }
    .pricing-card {
      width: 100%;
      max-width: 360px;
    }
  }
</style>
</head>
<body>

<header>
  <div class="container" role="banner">
    <h1 tabindex="0">Track Mate</h1>
    <nav aria-label="Primary Navigation">
      <ul>
        <li><a href="#features" tabindex="0">Features</a></li>
        <li><a href="#how-it-works" tabindex="0">How It Works</a></li>
        <li><a href="#testimonials" tabindex="0">Testimonials</a></li>
        <li><a href="#pricing" tabindex="0">Pricing</a></li>
        <li><a href="#contact" tabindex="0">Contact</a></li>
      </ul>
    </nav>
  </div>
</header>

<main>
  <section class="hero" role="region" aria-label="Introduction">
    <h2 tabindex="0">Track Mate - AI Bot for Order Management & Delivery Prediction</h2>
    <p tabindex="0">Solve your order tracking frustrations with our AI-powered bot that manages orders, predicts delivery delays, finds the best prices, and more – all in one place.</p>
    <button class="btn-primary" aria-label="Get started with Track Mate">Get Started</button>
  </section>

  <section id="features" class="container" role="region" aria-labelledby="features-title">
    <h3 id="features-title">Key Features & Functionalities</h3>
    <div class="features-grid">
      <article class="feature-card" tabindex="0" aria-label="Full order management ecosystem feature">
        <div class="feature-icon" aria-hidden="true">📦</div>
        <h4>Full Order Management Ecosystem</h4>
        <p>Track, cancel, return, and refund requests in one convenient place. Use voice commands for quick order status updates.</p>
      </article>
      <article class="feature-card" tabindex="0" aria-label="AI prediction model feature">
        <div class="feature-icon" aria-hidden="true">🤖</div>
        <h4>AI Prediction Model</h4>
        <p>Get real-time delivery delay predictions using weather, city conditions, and seller history data.</p>
      </article>
      <article class="feature-card" tabindex="0" aria-label="Smart negotiation bot feature">
        <div class="feature-icon" aria-hidden="true">💬</div>
        <h4>Smart Negotiation Bot</h4>
        <p>Automatically negotiate with sellers for discounts, coupons, and compensations during order delays.</p>
      </article>
      <article class="feature-card" tabindex="0" aria-label="Wallet and offer integration feature">
        <div class="feature-icon" aria-hidden="true">💰</div>
        <h4>Wallet & Offer Integration</h4>
        <p>Find lowest prices, cashback offers, and EMI options across multiple platforms for your orders.</p>
      </article>
      <article class="feature-card" tabindex="0" aria-label="Auto email and WhatsApp integration feature">
        <div class="feature-icon" aria-hidden="true">📧</div>
        <h4>Auto Email & WhatsApp Integration</h4>
        <p>Fetch order updates automatically and send notifications like shipping and delivery alerts.</p>
      </article>
      <article class="feature-card" tabindex="0" aria-label="Loyalty points and rewards feature">
        <div class="feature-icon" aria-hidden="true">🎁</div>
        <h4>Loyalty Points & Rewards System</h4>
        <p>Earn points for successful deliveries and redeem them for discounts, vouchers, or cashback.</p>
      </article>
      <article class="feature-card" tabindex="0" aria-label="Voice and chat AI assistant feature">
        <div class="feature-icon" aria-hidden="true">🎙️</div>
        <h4>Voice & Chat AI Assistant</h4>
        <p>Manage your orders, get delivery predictions, and status updates using our AI assistant similar to Siri or Alexa.</p>
      </article>
      <article class="feature-card" tabindex="0" aria-label="Pro version subscription model feature">
        <div class="feature-icon" aria-hidden="true">⭐</div>
        <h4>Pro Version (Subscription)</h4>
        <p>Access advanced features including bulk order management and enhanced analytics tailored for businesses.</p>
      </article>
    </div>
  </section>

  <section id="how-it-works" role="region" aria-labelledby="how-it-works-title" class="container">
    <h3 id="how-it-works-title">How Track Mate Works</h3>
    <div class="flow-container">
      <div class="step" tabindex="0">
        <div class="step-icon">1</div>
        <div class="step-content">
          <h5>Connect Your Accounts</h5>
          <p>Integrate your e-commerce accounts and communication channels like email and WhatsApp securely.</p>
        </div>
      </div>
      <div class="step" tabindex="0">
        <div class="step-icon">2</div>
        <div class="step-content">
          <h5>Automatic Order Tracking</h5>
          <p>Track and manage all your orders in a unified dashboard with real-time updates.</p>
        </div>
      </div>
      <div class="step" tabindex="0">
        <div class="step-icon">3</div>
        <div class="step-content">
          <h5>AI-Driven Delivery Predictions</h5>
          <p>Predict possible delivery delays using advanced AI models based on multiple data points.</p>
        </div>
      </div>
      <div class="step" tabindex="0">
        <div class="step-icon">4</div>
        <div class="step-content">
          <h5>Smart Negotiations & Offers</h5>
          <p>Bot automatically negotiates for discounts and finds the best price offers and cashback deals.</p>
        </div>
      </div>
      <div class="step" tabindex="0">
        <div class="step-icon">5</div>
        <div class="step-content">
          <h5>Loyalty Rewards & Voice Assistant</h5>
          <p>Earn loyalty points and engage with our voice assistant to get status updates anytime.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="testimonials" class="testimonials" role="region" aria-labelledby="testimonials-title">
    <h3 id="testimonials-title">What Users Say</h3>
    <div class="testimonial-cards">
      <figure class="testimonial-card" tabindex="0" aria-label="User testimonial from Jane Doe">
        <blockquote>
          Track Mate changed how I manage my online orders. I no longer worry about delays or lost packages – everything is tracked in one place!
        </blockquote>
        <figcaption class="testimonial-author">- Jane Doe</figcaption>
      </figure>
      <figure class="testimonial-card" tabindex="0" aria-label="User testimonial from Rajesh Kumar">
        <blockquote>
          The AI predictions are surprisingly accurate. It saved me time and hassle by alerting me about delays before it happened.
        </blockquote>
        <figcaption class="testimonial-author">- Rajesh Kumar</figcaption>
      </figure>
      <figure class="testimonial-card" tabindex="0" aria-label="User testimonial from Alicia Chen">
        <blockquote>
          Love the smart negotiation feature! I got discounts automatically when my order was delayed. It truly feels like having a personal assistant.
        </blockquote>
        <figcaption class="testimonial-author">- Alicia Chen</figcaption>
      </figure>
    </div>
  </section>

  <section id="pricing" class="container" role="region" aria-labelledby="pricing-title">
    <h3 id="pricing-title">Pricing Plans</h3>
    <div class="pricing-cards" role="list">
      <article class="pricing-card" tabindex="0" role="listitem" aria-label="Free plan pricing">
        <h4>Free</h4>
        <p class="price">₹0 <small>/ month</small></p>
        <ul>
          <li>Track orders on 2 platforms</li>
          <li>Basic delivery delay notifications</li>
          <li>Price comparison & cashback offers</li>
          <li>Auto email integration</li>
          <li>Community support</li>
        </ul>
        <button aria-label="Select Free Plan">Select Free</button>
      </article>
      <article class="pricing-card popular" tabindex="0" role="listitem" aria-label="Pro plan pricing">
        <h4>Pro</h4>
        <p class="price">₹499 <small>/ month</small></p>
        <ul>
          <li>Track unlimited orders & platforms</li>
          <li>Advanced AI delay predictions</li>
          <li>Smart negotiation bot</li>
          <li>Wallet & EMI offers integration</li>
          <li>Auto WhatsApp & email notifications</li>
          <li>Loyalty points & rewards system</li>
          <li>Priority support</li>
        </ul>
        <button aria-label="Select Pro Plan">Get Pro</button>
      </article>
    </div>
  </section>

  <section class="blog-section container" role="region" aria-labelledby="blog-title">
    <h3 id="blog-title">Blog & Resources</h3>
    <div class="blog-posts">
      <article class="blog-post" tabindex="0">
        <h5>5 Tips to Track Your E-commerce Orders Like a Pro</h5>
        <p>Learn best practices for monitoring your order statuses and avoiding surprises on delivery day.</p>
        <a href="#" aria-label="Read full article on tracking e-commerce orders">Read more &rarr;</a>
      </article>
      <article class="blog-post" tabindex="0">
        <h5>How AI is Changing Delivery Predictions</h5>
        <p>Discover the emerging AI technologies that make delivery time predictions more reliable and useful.</p>
        <a href="#" aria-label="Read full article on AI and delivery predictions">Read more &rarr;</a>
      </article>
      <article class="blog-post" tabindex="0">
        <h5>The Benefits of Smart Price Comparisons & Cashback Offers</h5>
        <p>Maximize your savings while shopping online with smart price tracking and offer alerts.</p>
        <a href="#" aria-label="Read full article on price comparison and cashback offers">Read more &rarr;</a>
      </article>
    </div>
  </section>

  <section id="contact" class="contact-section" role="region" aria-labelledby="contact-title">
    <h3 id="contact-title">Get In Touch</h3>
    <form aria-label="Contact form for Track Mate inquiries">
      <label for="name">Name</label>
      <input type="text" id="name" name="name" placeholder="Your full name" required />

      <label for="email">Email</label>
      <input type="email" id="email" name="email" placeholder="you@example.com" required />

      <label for="message">Message</label>
      <textarea id="message" name="message" placeholder="Write your message here..." required></textarea>

      <button type="submit" aria-label="Send message via contact form">Send Message</button>
    </form>
  </section>
</main>

<footer role="contentinfo">
  <p>© 2024 Track Mate. All rights reserved. | <a href="#privacy" aria-label="View privacy policy">Privacy Policy</a> &amp; <a href="#terms" aria-label="View terms of service">Terms of Service</a></p>
</footer>

</body>
</html>
