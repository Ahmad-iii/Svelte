

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
            <a href="#contact-us">CONTACT US</a>
          </div>
        </li>
      </ul>
      <button class="cta-button" on:click={openModal}>SignIn/SignUp</button>
    </nav>
  </div>

  <!-- Auth Modal -->
  <div class="auth-modal" class:active={isModalOpen}>
    <div 
      class="modal-overlay" 
      role="button"
      tabindex="0"
      on:click={closeModal}
      on:keydown={e => e.key === 'Enter' && closeModal()}
      aria-label="Close modal"
    ></div>
    <div class="modal-content">
      <button class="close-modal" on:click={closeModal}>×</button>
      
      <div class="auth-form">
        <h2>{isSignUp ? 'Sign Up' : 'Sign In'}</h2>
        
        <form on:submit|preventDefault={handleSubmit}>
          <div class="form-group">
            <input 
              type="email" 
              placeholder="Email"
              bind:value={email}
              class:error={emailError}
              on:focus={() => emailError = false}
            />
            {#if emailError}
              <span class="error-message">Please enter a valid email</span>
            {/if}
          </div>
          
          <div class="form-group password-group">
            <input 
              type={showPassword ? 'text' : 'password'}
              placeholder="Password"
              bind:value={password}
              class:error={passwordError}
              on:focus={() => passwordError = false}
            />
            <button 
              type="button" 
              class="toggle-password"
              on:click={() => showPassword = !showPassword}
            >
              {showPassword ? '👁️' : '👁️‍🗨️'}
            </button>
            {#if passwordError}
              <span class="error-message">Password is required</span>
            {/if}
          </div>
          
          <button type="submit" class="submit-btn">
            {isSignUp ? 'Sign Up' : 'Sign In'}
          </button>
        </form>
        
        <p class="toggle-mode">
          {#if isSignUp}
            Already have an account? 
            <button class="toggle-link" on:click={() => isSignUp = false}>
              Sign In
            </button>
          {:else}
            Don't have an account? 
            <button class="toggle-link" on:click={() => isSignUp = true}>
              Sign Up
            </button>
          {/if}
        </p>
      </div>
    </div>
  </div>

  <div class="header-content">
    <div class="header-title">NEXT GENERATION BOOKING ENGINE AND DIGITAL SALES PLATFORM</div>
    <div class="header-main-title">THE BOOKING ENGINE FOR <br>GROWTH</div>
    <div class="header-description">Stayify helps boutique hotels, hotel chains, resorts and travel brands to boost direct<br>bookings - driving sales, increasing profits, and enhancing the customer experience.</div>
    <button class="header-cta" on:click={openModal}>SPEAK TO EXPERT</button>
  </div>
  <section class="reveal-section">
    <div class="stayify-content">
      <div class="about">ABOUT STAYIFY</div>
      <h1>Stayify is the all-in-one booking engine<br> built  for modern hospitality.<div class="underline"></div></h1>
      <p class="desc">From accommodation and spa treatments to dining, activities, and rentals—Stayify lets your guests book everything in one seamless flow. Fully customizable and deeply integrated with your existing systems, Stayify helps you increase direct bookings, reduce manual work, and deliver a frictionless guest experience—all under your brand.</p>
      <h2>Create a consistent brand experience<br>throughout the booking journey<div class="underline"></div></h2>
      <p class="desc">With Stayify, your booking engine feels like a natural part of your website, not a separate tool. Guests stay within your branded environment from start to finish, whether they’re booking a room, a spa treatment, or a dinner table. It’s one smooth, on-brand experience that builds trust and drives more direct bookings.</p>
      <div class="cta-container"><button class="cta" on:click={openModal}>TALK TO US</button></div>
    </div>
  </section>

<div class="second-background">
  <div class="news-section">
    <div class="section-header">
      <div class="section-subtitle">NEWS & BLOG</div>
      <h2 class="section-title">What's New at Stayify</h2>
    </div>
    
    <div class="articles-grid">
      <article class="article-card">
        <img src="image1.png" 
             alt="Hotel Website Design" 
             class="article-image">
        <div class="article-content">
          <h3 class="article-title">A New Look, A Stronger Solution: Stayify's Updated Website for Hotel Success</h3>
          <div class="article-meta">
            <div class="date-icon"></div>
            <span class="article-date">June 18, 2025</span>
          </div>
          <p class="article-description">We're excited to unveil the all-new Stayify.com — redesigned with you in mind. Whether you're managing a single hotel or running a growing chain, we know the challenges you face.</p>
        </div>
      </article>
      
      <article class="article-card">
        <img src="image2.png" 
             alt="Hotel Booking Systems" 
             class="article-image">
        <div class="article-content">
          <h3 class="article-title">The Delusion of Multiple Booking Engines and a Single Brand</h3>
          <div class="article-meta">
            <div class="date-icon"></div>
            <span class="article-date">June 11, 2024</span>
          </div>
          <p class="article-description">The hospitality industry has a long history of building sales processes in silos, dating back to when airlines, accommodations, and rental cars were first linked through global data networks (GDS)...</p>
        </div>
      </article>
    </div>
  </div>
</div>
  <div class="cta-section">
    <div class="cta-content">
      <h3>Want to hear more about Stayify? Reach out to our team.</h3>
      <button class="contact-btn" on:click={openModal}>CONTACT US</button>
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

  /*********************************************
   * SHARED STYLES (Both Desktop and Mobile)
   *********************************************/

  /* Overlay for header section */
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

  /*********************************************
   * MOBILE-SPECIFIC COMPONENTS
   * These are only visible on mobile devices
   *********************************************/
  
  /* Mobile Menu Button */
  .hamburger-menu {
    display: none; /* Hidden by default, shown in mobile media query */
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
    background: rgba(81, 92, 213, 0.95);
    backdrop-filter: blur(10px);
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
    color: white;
    text-decoration: none;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 0;
    transition: all 0.3s ease;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
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

  /*********************************************
   * DESKTOP-SPECIFIC STYLES (min-width: 769px)
   * These styles override the base styles for desktop view
   *********************************************/
  /* Moved and enhanced desktop styles */
  @media (min-width: 769px) {
    /* Header Text Styles - Desktop Only */
    
    /* "NEXT GENERATION BOOKING ENGINE..." */
    .background .header-content .header-title {
      font-size: 17px !important;  /* Using !important to override base styles */
      line-height: 25px;
      letter-spacing: 0.16em;
      margin-bottom: 20px;
      padding-top: 40px;
    }

    /* "THE BOOKING ENGINE FOR GROWTH" */
    .background .header-content .header-main-title {
      font-size: 49px;
      line-height: 65px;
      margin-top: 40px;
      margin-bottom: 30px;
      padding: 0 20px;
    }

    /* "Stayify helps boutique hotels..." */
    .background .header-content .header-description {
      font-size: 23px;
      line-height: 37px;
      max-width: 996px;
      margin: 0 auto 40px;
      padding: 0 30px;
    }

    /* "SPEAK TO EXPERT" button */
    .background .header-content .header-cta {
      font-size: 19px;
      padding: 21px 41px;
      margin-top: 40px;
    }
  }

  /*********************************************
   * MOBILE-SPECIFIC STYLES (max-width: 768px)
   * These styles override the base styles for mobile view
   *********************************************/
  @media (max-width: 768px) {
    /* Navigation Elements - Mobile Only */
    .nav-links, .cta-button {
      display: none;
    }
    
    .navbar {
      padding: 15px 20px;
      justify-content: space-between;
      height: 90px;
      background: rgba(81, 92, 213, 0.1);
      backdrop-filter: blur(10px);
    }

    .hamburger-menu {
      display: flex;
      z-index: 1002;
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

  /*********************************************
   * BASE STYLES (Mobile First Approach)
   * These styles apply to all screen sizes unless
   * overridden by media queries
   *********************************************/

  /* Main Background */
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

  /* Base Header Styles */
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

  /* Second Background Section with News */
  .second-background {
    width: 100%;
    height: 100vh;
    background: url('/second_Background.png') center/cover no-repeat;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 80px 40px;
    z-index: 10;
  }

  /* News Section Styles */
  .news-section {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    position: relative;
    z-index: 12;
  }

  .section-header {
    text-align: center;
    margin-bottom: 60px;
  }

  .section-subtitle {
    font-family: 'Raleway', sans-serif;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: rgba(0, 0, 0, 0.8);
    margin-bottom: 16px;
  }

  .section-title {
    font-family: 'Raleway', sans-serif;
    font-size: 42px;
    font-weight: 700;
    color: rgb(0, 0, 0);
    line-height: 1.2;
    position: relative;
    text-shadow: 0px 0px 8px rgba(0, 0, 0, 0.5);
  }

  .section-title::after {
    content: '';
    position: absolute;
    bottom: -12px;
    left: 50%;
    transform: translateX(-50%);
    width: 80px;
    height: 4px;
    background: linear-gradient(90deg, #8b5cf6, #a855f7);
    border-radius: 2px;
  }

  .articles-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    margin-top: 20px;
  }

  .article-card {
    background: rgba(255, 255, 255, 0.15);
    border-radius: 16px;
    overflow: hidden;
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    transition: transform 0.3s ease, background-color 0.3s ease;
  }

  .article-card:hover {
    transform: translateY(-8px);
    background: rgba(255, 255, 255, 0.25);
  }

  .article-image {
    width: 100%;
    height: 240px;
    object-fit: cover;
    transition: transform 0.3s ease;
  }

  .article-card:hover .article-image {
    transform: scale(1.05);
  }

  .article-content {
    padding: 32px;
  }

  .article-title {
    font-family: 'Raleway', sans-serif;
    font-size: 24px;
    font-weight: 700;
    color: rgb(0, 0, 0);
    line-height: 1.3;
    margin-bottom: 20px;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .article-meta {
    display: flex;
    align-items: center;
    margin-bottom: 16px;
  }

  .date-icon {
    width: 16px;
    height: 16px;
    background: linear-gradient(45deg, #8b5cf6, #a855f7);
    border-radius: 3px;
    margin-right: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .date-icon::before {
    content: '';
    width: 8px;
    height: 8px;
    background: white;
    border-radius: 1px;
  }

  .article-date {
    font-family: 'Raleway', sans-serif;
    font-size: 14px;
    color: #8b5cf6;
    font-weight: 600;
  }

  .article-description {
    font-family: 'Raleway', sans-serif;
    font-size: 16px;
    color: rgba(0, 0, 0, 0.9);
    line-height: 1.6;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
    
  }

  /* Mobile styles for news section */
  @media (max-width: 768px) {
    .second-background {
      padding: 40px 16px;
      height: auto;
      min-height: 100vh;
    }

    .articles-grid {
      grid-template-columns: 1fr;
      gap: 20px;
    }
    
    .section-title {
      font-size: 28px;
    }

    .section-subtitle {
      font-size: 12px;
    }

    .article-card {
      border-radius: 12px;
    }

    .article-image {
      height: 160px;
    }

    .article-content {
      padding: 20px;
    }

    .article-title {
      font-size: 18px;
      margin-bottom: 16px;
    }

    .article-description {
      font-size: 14px;
      line-height: 1.5;
      -webkit-line-clamp: 2;
      line-clamp: 2;
    }
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

  /* Modal Styles */
  .auth-modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
    z-index: 1000;
  }

  .auth-modal.active {
    opacity: 1;
    visibility: visible;
  }

  .modal-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(4px);
  }

  .modal-content {
    position: relative;
    width: 90%;
    max-width: 400px;
    background: white;
    border-radius: 16px;
    padding: 2rem;
    transform: translateY(20px);
    transition: transform 0.3s ease;
    z-index: 1001;
  }

  .auth-modal.active .modal-content {
    transform: translateY(0);
  }

  .close-modal {
    position: absolute;
    top: 1rem;
    right: 1rem;
    background: none;
    border: none;
    font-size: 24px;
    color: rgba(1, 22, 39, 0.5);
    cursor: pointer;
    padding: 0.5rem;
    line-height: 1;
    transition: color 0.2s ease;
  }

  .close-modal:hover {
    color: rgba(1, 22, 39, 0.8);
  }

  .auth-form h2 {
    font-family: 'Raleway', Arial, sans-serif;
    font-size: 24px;
    font-weight: 700;
    color: rgb(1, 22, 39);
    margin-bottom: 1.5rem;
    text-align: center;
  }

  .form-group {
    margin-bottom: 1rem;
    position: relative;
  }

  .form-group input {
    width: 100%;
    padding: 0.75rem 1rem;
    border: 2px solid rgba(1, 22, 39, 0.1);
    border-radius: 8px;
    font-family: 'Raleway', Arial, sans-serif;
    font-size: 16px;
    transition: border-color 0.2s ease;
  }

  .form-group input:focus {
    outline: none;
    border-color: #515CD5;
  }

  .form-group input.error {
    border-color: #ff4444;
  }

  .error-message {
    color: #ff4444;
    font-size: 12px;
    margin-top: 0.25rem;
    display: block;
  }

  .password-group {
    position: relative;
  }

  .toggle-password {
    position: absolute;
    right: 1rem;
    top: 50%;
    transform: translateY(-50%);
    background: none;
    border: none;
    cursor: pointer;
    padding: 0.25rem;
    font-size: 16px;
  }

  .submit-btn {
    width: 100%;
    padding: 0.75rem;
    background: #515CD5;
    color: white;
    border: none;
    border-radius: 30px;
    font-family: 'Raleway', Arial, sans-serif;
    font-weight: 700;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.2s ease;
    margin-top: 1rem;
  }

  .submit-btn:hover {
    background: #6EC1E4;
  }

  .toggle-mode {
    text-align: center;
    margin-top: 1rem;
    font-family: 'Raleway', Arial, sans-serif;
    color: rgba(1, 22, 39, 0.7);
  }

  .toggle-link {
    background: none;
    border: none;
    color: #515CD5;
    font-weight: 700;
    cursor: pointer;
    padding: 0;
    margin-left: 0.25rem;
    transition: color 0.2s ease;
  }

  .toggle-link:hover {
    color: #6EC1E4;
  }

  @media (max-width: 480px) {
    .modal-content {
      padding: 1.5rem;
    }

    .auth-form h2 {
      font-size: 20px;
    }

    .form-group input {
      font-size: 14px;
    }
  }
</style>

<script lang="ts">
  // Mobile menu state
  let mobileMenuOpen = false;
  let activeDropdown: number | null = null;

  // Modal state
  let isModalOpen = false;
  let isSignUp = true;
  let email = '';
  let password = '';
  let emailError = false;
  let passwordError = false;
  let showPassword = false;

  import { goto } from '$app/navigation';

  // Modal functions
  function openModal(): void {
    isModalOpen = true;
    document.body.style.overflow = 'hidden';
  }

  function closeModal(): void {
    isModalOpen = false;
    document.body.style.overflow = '';
    // Reset form
    email = '';
    password = '';
    emailError = false;
    passwordError = false;
    showPassword = false;
  }

  function handleSubmit(): void {
    // Reset errors
    emailError = false;
    passwordError = false;

    // Simple validation
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!emailRegex.test(email)) {
      emailError = true;
    }
    if (!password) {
      passwordError = true;
    }

    if (!emailError && !passwordError) {
      // Navigate to appropriate response page
      if (isSignUp) {
        goto('/sign-up');
      } else {
        goto('/sign-in');
      }
      closeModal();
    }
  }

  // Mobile menu functions
  function toggleMobileMenu(): void {
    mobileMenuOpen = !mobileMenuOpen;
    document.querySelector('.hamburger-menu')?.classList.toggle('active');
    
    if (mobileMenuOpen) {
      document.body.style.overflow = 'hidden';
    } else {
      document.body.style.overflow = '';
      activeDropdown = null;
      document.querySelectorAll('.mobile-nav-links .dropdown')
        .forEach(dropdown => dropdown.classList.remove('active'));
    }
  }

  function closeMobileMenu(): void {
    mobileMenuOpen = false;
    document.querySelector('.hamburger-menu')?.classList.remove('active');
    document.body.style.overflow = '';
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
