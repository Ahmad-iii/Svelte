

<div class="background">
  <div class="transparent-overlay">
    <nav class="navbar">
      <div class="nav-logo">
        <img src="/logo.png" alt="Logo" height="40"/>
      </div>
      <button 
        class="hamburger-menu" 
        class:active={mobileMenuOpen} 
        aria-label="Menu" 
        on:click={toggleMobileMenu}
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
      <div class="mobile-menu" class:active={mobileMenuOpen}>
        <button class="close-menu" aria-label="Close menu" on:click={closeMobileMenu}>×</button>
        <ul class="mobile-nav-links">
          <li><a href="#home" class="active">HOME</a></li>
          <li><a href="#platform">PLATFORM</a></li>
          <li><a href="#solutions">SOLUTIONS</a></li>
          <li><a href="#agency">AGENCY</a></li>
          <li class="dropdown" class:active={activeDropdown === 0}>
            <a href="#cases" on:click={(e) => handleDropdownClick(e, 0)}>CASES <span class="arrow">▼</span></a>
            <div class="dropdown-content" class:active={activeDropdown === 0}>
              <a href="#hotel">HOTEL DE STERRENBERG</a>
            </div>
          </li>
          <li><a href="#partners">PARTNERS</a></li>
          <li class="dropdown" class:active={activeDropdown === 1}>
            <a href="#about" on:click={(e) => handleDropdownClick(e, 1)}>ABOUT <span class="arrow">▼</span></a>
            <div class="dropdown-content" class:active={activeDropdown === 1}>
              <a href="#contact">CONTACT US</a>
            </div>
          </li>
        </ul>
        <button class="mobile-cta">BOOK A MEETING</button>
      </div>
      <ul class="nav-links">
        <li><a href="#home" class="active">HOME</a></li>
        <li><a href="#platform">PLATFORM</a></li>
        <li><a href="#solutions">SOLUTIONS</a></li>
        <li><a href="#agency">AGENCY</a></li>
        <li class="dropdown">
          <a href="#cases">CASES <span class="arrow">▼</span></a>
          <div class="dropdown-content">
            <a href="#hotel">HOTEL DE STERRENBERG</a>
          </div>
        </li>
        <li><a href="#partners">PARTNERS</a></li>
        <li class="dropdown">
          <a href="#about">ABOUT <span class="arrow">▼</span></a>
          <div class="dropdown-content">
            <a href="#contact">CONTACT US</a>
          </div>
        </li>
      </ul>
      <button class="cta-button">SignIn/SignUp</button>
    </nav>
  </div>
  <div class="header-content">
    <div class="header-title">NEXT GENERATION BOOKING ENGINE AND DIGITAL SALES PLATFORM</div>
    <div class="header-main-title">THE BOOKING ENGINE FOR <br>GROWTH</div>
    <div class="header-description">Stayify helps boutique hotels, hotel chains, resorts and travel brands to boost direct<br>bookings - driving sales, increasing profits, and enhancing the customer experience.</div>
    <button class="header-cta">SPEAK TO EXPERT</button>
  </div>
  <section class="reveal-section">
    <div class="stayify-content">
      <div class="about">ABOUT STAYIFY</div>
      <h1>Stayify is the all-in-one booking engine<br> built  for modern hospitality.<div class="underline"></div></h1>
      <p class="desc">From accommodation and spa treatments to dining, activities, and rentals—Stayify lets your guests book everything in one seamless flow. Fully customizable and deeply integrated with your existing systems, Stayify helps you increase direct bookings, reduce manual work, and deliver a frictionless guest experience—all under your brand.</p>
      <h2>Create a consistent brand experience<br>throughout the booking journey<div class="underline"></div></h2>
      <p class="desc">With Stayify, your booking engine feels like a natural part of your website, not a separate tool. Guests stay within your branded environment from start to finish, whether they’re booking a room, a spa treatment, or a dinner table. It’s one smooth, on-brand experience that builds trust and drives more direct bookings.</p>
      <div class="cta-container"><button class="cta">TALK TO US</button></div>
    </div>
  </section>

<div class="second-background"></div>
  <div class="cta-section">
    <div class="cta-content">
      <h3>Want to hear more about Stayify? Reach out to our team.</h3>
      <button class="contact-btn">CONTACT US</button>
    </div>
  </div>
  <div class="footer-wrapper">
    <div class="footer-background">
      <img src="/footer.png" alt="Footer Background" class="footer-image" />
    </div>
  </div>
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;700&display=swap');

  .transparent-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 70vh;
    background: transparent;
    z-index: 1;
    pointer-events: none;
  }

  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    pointer-events: auto;
    height: 70px;
    padding: 0 40px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    z-index: 1;
  }

  .nav-logo img {
    height: 250px;
    width: auto;
    margin-top: 48px ;
    margin-left: -18px;
  }

  .nav-links {
    display: flex;
    gap: 32px;
    list-style: none;
    margin-top: 30px;
    padding: 0;
    margin-left: auto;
    margin-right: 32px;
  }

  .nav-links a {
    font-family: 'Raleway', sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 70px;
    color: rgba(255, 255, 255, 0.85);
    text-decoration: none;
    transition: all 0.3s ease;
    white-space: nowrap;
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }

  .nav-links a:hover {
    color: rgb(255, 255, 255);
    text-shadow: 0 0 8px rgba(255,255,255,0.5);
    cursor: pointer;
  }

  .nav-links a.active {
    color: rgb(255, 255, 255);
    text-shadow: 0 0 8px rgba(255,255,255,0.5);
  }

  .arrow {
    font-size: 12px;
    margin-left: 4px;
  }

  .dropdown {
    position: relative;
  }

  .dropdown-content {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    min-width: 200px;
    z-index: 2;
  }

  .dropdown-content a {
    line-height: 50px;
    padding: 0 20px;
    display: block;
    color: white;
    background-color: #484698;
  }

  .dropdown:hover .dropdown-content {
    display: block;
  }

  .cta-button {
    background-color: #515CD5;
    color: rgb(255, 255, 255);
    font-family: 'Raleway', sans-serif;
    font-style: normal;
    font-weight: 700;
    font-size: 18px;
    line-height: 28px;
    padding: 8px 24px;
    border-radius: 30px;
    border: none;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-top: 30px;
  }

  .cta-button:hover {
    background-color: #55778F;
    box-shadow: 0 4px 12px rgba(81, 92, 213, 0.3);
    transform: translateY(-1px);
  }

  /* Mobile Menu Styles */
  .hamburger-menu {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    width: 40px;
    background: #515CD5;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    padding: 12px;
    position: fixed;
    top: 25px;
    right: 20px;
    z-index: 1001;
  }

  .hamburger-menu span {
    display: block;
    width: 100%;
    height: 2px;
    background-color: white;
    transition: all 0.3s ease;
    margin: 2px 0;
    transform-origin: center;
  }

  .hamburger-menu.active span:nth-child(1) {
    transform: translateY(8px) rotate(45deg);
  }

  .hamburger-menu.active span:nth-child(2) {
    opacity: 0;
  }

  .hamburger-menu.active span:nth-child(3) {
    transform: translateY(-8px) rotate(-45deg);
  }

  .mobile-menu {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: white;
    padding: 20px;
    z-index: 1000;
    opacity: 0;
    transform: translateX(-100%);
    transition: transform 0.3s ease, opacity 0.3s ease;
  }

  .mobile-menu.active {
    display: block;
    opacity: 1;
    transform: translateX(0);
  }

  .close-menu {
    position: absolute;
    top: 20px;
    right: 20px;
    font-size: 32px;
    background: none;
    border: none;
    color: #515CD5;
    cursor: pointer;
  }

  .mobile-nav-links {
    margin-top: 80px;
    list-style: none;
    padding: 0;
  }

  .mobile-nav-links li {
    margin: 0;
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  }

  .mobile-nav-links li:first-child {
    border-top: 1px solid rgba(0, 0, 0, 0.1);
  }

  .mobile-nav-links a {
    font-family: 'Raleway', sans-serif;
    font-size: 20px;
    color: #333;
    text-decoration: none;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 0;
    transition: all 0.3s ease;
  }

  .mobile-nav-links .dropdown-content {
    display: none;
    background: #f8f8f8;
    padding-left: 20px;
  }

  .mobile-nav-links .dropdown-content.active {
    display: block;
  }

  .mobile-nav-links .dropdown-content a {
    font-size: 18px;
    padding: 15px 0;
    color: #666;
  }

  .mobile-nav-links .arrow {
    transition: transform 0.3s ease;
  }

  .mobile-nav-links .dropdown.active .arrow {
    transform: rotate(180deg);
  }

  .mobile-cta {
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    background: #515CD5;
    color: white;
    font-family: 'Raleway', sans-serif;
    font-weight: 700;
    padding: 15px 30px;
    border: none;
    border-radius: 30px;
    font-size: 16px;
    cursor: pointer;
  }

  /* Desktop Styles (min-width: 769px) */
  /* These styles will override the base styles for desktop view only */
  @media (min-width: 769px) {
    /* Header Section Text Styles - Desktop */
    .header-title {
      font-size: 16px;
      line-height: 24px;
      letter-spacing: 0.16em;
    }

    .header-main-title {
      font-size: 48px;
      line-height: 64px;
      margin-top: 40px;
    }

    .header-description {
      font-size: 22px;
      line-height: 36px;
      max-width: 996px;
    }

    .header-cta {
      font-size: 18px;
      padding: 20px 40px;
    }
  }

  /* Mobile Styles (max-width: 768px) */
  @media (max-width: 768px) {
    /* Navigation Elements - Mobile */
    .nav-links, .cta-button {
      display: none;
    }
    
    .navbar {
      padding: 15px 20px;
      justify-content: space-between;
      height: 60px;
    }

    .hamburger-menu {
      display: flex;
    }

    .nav-logo img {
      height: 180px;
      margin: 0;
      width: auto;
      position: fixed;
      top: -35px;
      left: 12px;
    }

    .header-content {
      padding: 0;
      height: auto;
      min-height: 100vh;
      justify-content: flex-start;
    }

    .header-content > * {
      padding-left: 16px;
      padding-right: 16px;
    }

    .header-title {
      font-size: 14px;
      line-height: 1.4;
      margin-top: 51px;
      letter-spacing: 0.12em;
      max-width: 335px;
      margin-left: auto;
      margin-right: auto;
      text-align: center;
    }

    .header-main-title {
      font-size: 36px;
      line-height: 48px;
      margin-top: 50px;
      text-shadow: 0px 0px 8px rgba(0, 0, 0, 0.5);
      max-width: 335px;
      margin-left: auto;
      margin-right: auto;
      text-align: center;
      padding-left: 24px;
      padding-right: 24px;
      br {
        display: none;
      }
    }

    .header-description {
      font-size: 18px;
      line-height: 24px;
      margin-top: 24px;
      text-align: center;
      max-width: 335px;
      margin-left: auto;
      margin-right: auto;
      padding-left: 24px;
      padding-right: 24px;
      br {
        display: none;
      }
    }

    .header-cta {
      margin-top: 32px;
      padding: 16px 32px;
      font-size: 16px;
      min-width: 200px;
      text-align: center;
      display: inline-block;
    }
  }

  .background {
    min-height: 200vh;
    width: 100%;
    background-image: url('/headerBackground.png');
    background-size: cover;
    background-position: center top;
    background-repeat: no-repeat;
    background-attachment: fixed;
    position: relative;
    overflow: hidden;
    scroll-behavior: smooth;
    -webkit-overflow-scrolling: touch;
  }

  /* Base Header Styles (Mobile First) */
  /* These styles serve as the foundation and will be overridden by desktop styles where needed */
  
  /* Header Container */
  .header-content {
    height: 100vh;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    padding-top: 111px;
    gap: 32px;
  }

  /* Main Title Text */
  .header-title {
    font-family: 'Raleway', sans-serif;
    font-style: normal;
    font-weight: 700;
    font-size: 12px;
    line-height: 17px;
    color: rgb(255, 255, 255);
    text-align: center;
    letter-spacing: 0.16em;
  }

  /* Large Title Text */
  .header-main-title {
    font-family: 'Raleway', sans-serif;
    font-style: normal;
    font-weight: 700;
    font-size: 33px;
    line-height: 54px;
    color: rgb(255, 255, 255);
    text-align: center;
    text-shadow: 0px 0px 6px rgba(0, 0, 0, 0.97);
    margin-top: 69px;
    padding-bottom: 21px;
  }

  /* Description Text */
  .header-description {
    font-family: 'Raleway', sans-serif;
    font-style: normal;
    font-weight: 700;
    font-size: 18px;
    line-height: 30px;
    color: rgb(255, 255, 255);
    text-align: center;
    text-shadow: 0px 0px 6px rgba(0, 0, 0, 0.97);
    max-width: 996px;
    margin: -39px auto;
  }

  /* Call to Action Button */
  .header-cta {
    font-family: 'Raleway', sans-serif;
    font-style: normal;
    font-weight: 700;
    font-size: 15px;
    line-height: 15px;
    color: rgb(255, 255, 255);
    background-color: #515CD5;
    padding: 16px 32px;
    border-radius: 30px;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-top: 32px;
  }

  .header-cta:hover {
    background-color: transparent;
    color: rgb(255, 255, 255);
  }

  .reveal-section {
    position: sticky;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    height: 70vh;
    background: #fff;
    box-shadow: 0 8px 32px rgba(0,0,0,0.08);
    display: flex;
    align-items: center;
    justify-content: center;
    animation: slideUp 1s cubic-bezier(0.77,0,0.175,1) both;
    will-change: transform;
    overflow: hidden;
    z-index: 10;
    padding: 40px 0;
  }

  @media (max-width: 900px) {
    .reveal-section {
      height: auto;
      min-height: auto;
      padding: 30px 0;
      margin-bottom: 0;
    }

    .about {
      margin-top: 0;
    }
    
    .cta-section {
      padding: 40px 16px;
    }
    
    .cta-content {
      flex-direction: column;
      align-items: center;
    }
    
    .cta-content h3 {
      font-size: 18px;
      line-height: 24px;
      text-align: center;
    }

    .cta-container {
      padding-bottom: 0;
      margin: 1rem 0 0 0;
    }

    .stayify-content {
      padding: 1rem;
      justify-content: flex-start;
      gap: 1rem;
      height: auto;
    }
  }

  @keyframes slideUp {
    from {
      transform: translateY(100%);
      opacity: 0;
    }
    to {
      transform: translateY(0);
      opacity: 1;
    }
  }

  .stayify-content {
    max-width: 1100px;
    margin: 0 auto;
    text-align: center;
    font-family: 'Raleway', Arial, sans-serif;
    color: rgb(1, 22, 39);
    padding: 1.5rem;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    height: 100%;
    position: relative;
  }
  .about {
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 14px;
    color: rgba(1, 22, 39, 0.35);
    line-height: 17px;
    letter-spacing: 0.18em;
    margin-bottom: 1rem;
    margin-top: -1rem;
    text-transform: uppercase;
    width: 100%;
    text-align: center;
    display: block;
  }
  .stayify-content h1, .stayify-content h2 {
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 34px;
    line-height: 44px;
    color: rgb(1, 22, 39);
    margin-bottom: 1.1rem;
    margin-top: 0;
    width: 100%;
    text-align: center;
    display: block;
  }
  .stayify-content h2 {
    margin: 2.5rem 0 1.1rem 0;
  }
  .desc {
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    color: rgba(1, 22, 39, 0.75);
    margin-bottom: 0.9rem;
    margin-top: 0;
    text-align: center;
    width: 100%;
    display: block;
  }
  .underline {
    width: auto;
    height: 0px;
    background: #6c3ef4;
    margin: 1rem auto 1.5rem auto;
    border-radius: 2px;
    display: block;
  }
  .cta-container {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 1rem;
  }
  .cta {
    background: #513CDA;
    color: #fff;
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 15px;
    line-height: 15px;
    border: none;
    border-radius: 2rem;
    padding: 0.9rem 2.5rem;
    cursor: pointer;
    box-shadow: 0 2px 12px rgba(108,62,244,0.12);
    transition: background 0.2s;
    letter-spacing: 0.02em;
    margin: 0 auto;
    display: block;
  }
  .cta:hover {
    background: #6EC1E482;
  }

  .second-background {
    width: 100%;
    height: 100vh;
    background: url('/second_Background.png') center/cover no-repeat;
    position: sticky;
    top: 0;
    left: 0;
    right: 0;
    z-index: 10;
    margin: 0;
    padding: 0;
    transform: translateZ(0);
    backface-visibility: hidden;
    will-change: transform;
  }

  .cta-section {
    width: 100%;
    background: #fff;
    padding: 45px 24px;
    text-align: center;
    position: relative;
    z-index: 1;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .cta-content {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 30px;
    flex-wrap: wrap;
    padding: 0 20px;
  }

  .cta-content h3 {
    font-family: 'Raleway', Arial, sans-serif;
    font-size: 23px;
    color: rgb(1, 22, 39);
    margin: 0;
    font-weight: 700;
    line-height: 30px;
  }

  .contact-btn {
    background: #595FDA;
    color: #fff;
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 15px;
    line-height: 15px;
    border: none;
    border-radius: 50px;
    padding: 16px 32px;
    cursor: pointer;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    transition: background-color 0.2s ease;
    display: inline-block;
    margin: 0 auto;
    }

  .contact-btn:hover {
    background: #6EC1E482;
  }

  .footer-wrapper {
    width: 100%;
    position: relative;
    z-index: 1;
  }

  .footer-background {
    width: 100%;
    position: relative;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: flex-start;
  }

  .footer-image {
    width: 100%;
    height: auto;
    min-height: 160px;
    display: block;
    object-fit: cover;
  }

  @media (max-width: 900px) {
    .footer-image {
      min-height: 150px;
      object-position: center;
    }
  }
</style>

<script lang="ts">
  let mobileMenuOpen = false;
  let activeDropdown: number | null = null;

  function toggleMobileMenu(): void {
    mobileMenuOpen = !mobileMenuOpen;
    document.querySelector('.hamburger-menu')?.classList.toggle('active');
    
    if (!mobileMenuOpen) {
      activeDropdown = null;
      document.querySelectorAll('.mobile-nav-links .dropdown')
        .forEach(dropdown => dropdown.classList.remove('active'));
    }
  }

  function closeMobileMenu(): void {
    mobileMenuOpen = false;
    document.querySelector('.hamburger-menu')?.classList.remove('active');
    activeDropdown = null;
    document.querySelectorAll('.mobile-nav-links .dropdown')
      .forEach(dropdown => dropdown.classList.remove('active'));
  }

  function handleDropdownClick(event: MouseEvent, dropdownIndex: number): void {
    event.preventDefault();
    const dropdowns = document.querySelectorAll('.mobile-nav-links .dropdown');
    if (activeDropdown === dropdownIndex) {
      dropdowns[dropdownIndex].classList.remove('active');
      activeDropdown = null;
    } else {
      dropdowns.forEach((dropdown, index) => {
        if (index === dropdownIndex) {
          dropdown.classList.add('active');
        } else {
          dropdown.classList.remove('active');
        }
      });
      activeDropdown = dropdownIndex;
    }
  }
</script>
