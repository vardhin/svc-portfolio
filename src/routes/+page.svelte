<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Linden+Hill:ital@0;1&display=swap" rel="stylesheet">
</svelte:head>

<!-- Background image -->
<div class="background-image"></div>

<script>
  let activeSection = 'interior-design'; // Default active section
  let isMobileMenuOpen = false; // Add mobile menu state

  const sections = {
    'interior-design': {
      title: 'Interior Design Excellence',
      description: 'Transform your spaces with our innovative interior design solutions. From residential homes to commercial spaces, we bring your vision to life with creativity and precision.',
      timeline: [
        { year: '2020', project: 'Modern Villa Renovation', description: 'Complete interior makeover of a 4-bedroom villa with contemporary design elements and smart home integration.' },
        { year: '2021', project: 'Corporate Office Design', description: 'Designed a 10,000 sq ft office space for a tech company with open layouts and collaborative workspaces.' },
        { year: '2022', project: 'Luxury Apartment Complex', description: 'Interior design for 50 premium apartments featuring high-end finishes and modern amenities.' },
        { year: '2023', project: 'Restaurant Chain Interiors', description: 'Designed interiors for 5 restaurant locations with cohesive branding and efficient layouts.' }
      ],
      images: [
        'https://images.unsplash.com/photo-1586023492125-27b2c045efd7?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1567538096630-e0c55bd6374c?w=400&h=300&fit=crop'
      ]
    },
    'event-organization': {
      title: 'Memorable Event Organization',
      description: 'Creating unforgettable experiences through meticulous event planning and execution. From intimate gatherings to grand celebrations, we handle every detail.',
      timeline: [
        { year: '2020', project: 'Wedding Extravaganza', description: 'Organized a 500-guest wedding with traditional and modern elements, complete with custom decorations.' },
        { year: '2021', project: 'Corporate Annual Meet', description: 'Managed a 3-day corporate conference with international speakers and networking events.' },
        { year: '2022', project: 'Cultural Festival', description: 'Coordinated a week-long cultural festival featuring local artists, food vendors, and entertainment.' },
        { year: '2023', project: 'Product Launch Event', description: 'Executed a high-profile product launch for a tech company with 1000+ attendees and live streaming.' }
      ],
      images: [
        'https://images.unsplash.com/photo-1519167758481-83f550bb49b3?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1464366400600-7168b8af9bc3?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1511795409834-ef04bbd61622?w=400&h=300&fit=crop'
      ]
    },
    'civil-work': {
      title: 'Civil Engineering & Construction',
      description: 'Building strong foundations for the future with our comprehensive civil engineering services. From infrastructure development to structural design.',
      timeline: [
        { year: '2020', project: 'Residential Complex', description: 'Constructed a 100-unit residential complex with modern amenities and earthquake-resistant design.' },
        { year: '2021', project: 'Highway Bridge Project', description: 'Designed and built a 2-km highway bridge connecting two major districts.' },
        { year: '2022', project: 'Commercial Plaza', description: 'Developed a 5-story commercial plaza with retail spaces, offices, and parking facilities.' },
        { year: '2023', project: 'Water Treatment Plant', description: 'Constructed a state-of-the-art water treatment facility serving 50,000 residents.' }
      ],
      images: [
        'https://images.unsplash.com/photo-1541888946425-d81bb19240f5?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1589939705384-5185137a7f0f?w=400&h=300&fit=crop'
      ]
    },
    'publicity': {
      title: 'Publicity & Advertising Services',
      description: 'Amplify your brand presence with our strategic publicity and advertising solutions. From digital campaigns to traditional media, we ensure maximum impact.',
      timeline: [
        { year: '2020', project: 'Digital Marketing Campaign', description: 'Launched a comprehensive digital campaign for a startup, achieving 300% increase in brand awareness.' },
        { year: '2021', project: 'Television Commercial', description: 'Produced and aired a regional TV commercial for a consumer goods company.' },
        { year: '2022', project: 'Social Media Strategy', description: 'Developed social media presence for 10+ local businesses, increasing engagement by 250%.' },
        { year: '2023', project: 'Outdoor Advertising', description: 'Designed and installed billboard campaigns across 15 strategic locations in the city.' }
      ],
      images: [
        'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1553830591-fddf9c346e35?w=400&h=300&fit=crop',
        'https://images.unsplash.com/photo-1432888622747-4eb9a8efeb07?w=400&h=300&fit=crop'
      ]
    }
  };

  function setActiveSection(section) {
    activeSection = section;
    isMobileMenuOpen = false; // Close menu when section is selected
  }

  function toggleMobileMenu() {
    isMobileMenuOpen = !isMobileMenuOpen;
  }
</script>

<nav class="navbar">
  <div class="nav-container">
    <!-- Left-aligned brand -->
    <div class="brand">
      <div class="brand-content">
        <span class="brand-text">Satyam Vision Creators</span>
        <span class="brand-caption">we create your dreams</span>
      </div>
    </div>
    
    <!-- Hamburger menu button - only visible on smaller screens -->
    <button class="hamburger-btn" on:click={toggleMobileMenu} class:active={isMobileMenuOpen}>
      <span></span>
      <span></span>
      <span></span>
    </button>
  </div>
</nav>

<!-- Desktop pill bar - hidden on mobile -->
<div class="pill-bar desktop-only">
  <div class="pill-container">
    <button class="nav-pill {activeSection === 'interior-design' ? 'active' : ''}" 
            on:click={() => setActiveSection('interior-design')}>
      Interior Design
    </button>
    <button class="nav-pill {activeSection === 'event-organization' ? 'active' : ''}" 
            on:click={() => setActiveSection('event-organization')}>
      Event Organization
    </button>
    <button class="nav-pill {activeSection === 'civil-work' ? 'active' : ''}" 
            on:click={() => setActiveSection('civil-work')}>
      Civil Work
    </button>
    <button class="nav-pill {activeSection === 'publicity' ? 'active' : ''}" 
            on:click={() => setActiveSection('publicity')}>
      Publicity & Ads
    </button>
  </div>
</div>

<!-- Mobile menu overlay -->
<div class="mobile-menu-overlay" class:open={isMobileMenuOpen} on:click={toggleMobileMenu}></div>

<!-- Mobile menu -->
<div class="mobile-menu" class:open={isMobileMenuOpen}>
  <div class="mobile-menu-content">
    <button class="mobile-nav-item {activeSection === 'interior-design' ? 'active' : ''}" 
            on:click={() => setActiveSection('interior-design')}>
      Interior Design
    </button>
    <button class="mobile-nav-item {activeSection === 'event-organization' ? 'active' : ''}" 
            on:click={() => setActiveSection('event-organization')}>
      Event Organization
    </button>
    <button class="mobile-nav-item {activeSection === 'civil-work' ? 'active' : ''}" 
            on:click={() => setActiveSection('civil-work')}>
      Civil Work
    </button>
    <button class="mobile-nav-item {activeSection === 'publicity' ? 'active' : ''}" 
            on:click={() => setActiveSection('publicity')}>
      Publicity & Ads
    </button>
  </div>
</div>

<!-- Content Section -->
<main class="main-content">
  <div class="content-container">
    <section class="hero-section">
      <h1>{sections[activeSection].title}</h1>
      <p class="hero-description">{sections[activeSection].description}</p>
    </section>

    <!-- Portfolio Images -->
    <section class="portfolio-section">
      <h2>Our Work</h2>
      <div class="image-gallery">
        {#each sections[activeSection].images as image, index}
          <div class="image-item">
            <img src={image} alt="Portfolio work {index + 1}" loading="lazy" />
          </div>
        {/each}
      </div>
    </section>

    <!-- Timeline -->
    <section class="timeline-section">
      <h2>Project Timeline</h2>
      <div class="timeline">
        {#each sections[activeSection].timeline as item}
          <div class="timeline-item">
            <div class="timeline-year">{item.year}</div>
            <div class="timeline-content">
              <h3>{item.project}</h3>
              <p>{item.description}</p>
            </div>
          </div>
        {/each}
      </div>
    </section>
  </div>
</main>

<style>
  :global(*) {
    box-sizing: border-box;
  }

  :global(body) {
    margin: 0;
    padding: 0;
    overflow-x: hidden;
  }

  /* Background image styles */
  .background-image {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-image: url('/eye1.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    filter: grayscale(100%) blur(1px);
    z-index: -1;
  }

  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: transparent !important;
    backdrop-filter: none;
    -webkit-backdrop-filter: none;
    z-index: 1000;
    font-family: 'Linden Hill', serif;
    min-height: 60px;
  }

  .nav-container {
    max-width: 1200px;
    margin: 0;
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    padding: 1rem 1.5rem;
    min-height: 60px;
    background: transparent !important;
  }

  .brand {
    display: flex;
    align-items: center;
  }

  .brand-content {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .brand-text {
    font-size: clamp(1.5rem, 4vw, 2.5rem);
    font-weight: 900;
    color: #ffffff;
    letter-spacing: -0.025em;
    line-height: 1.1;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8), 0 0 20px rgba(0, 0, 0, 0.5);
  }

  .brand-caption {
    font-size: clamp(1rem, 2.5vw, 1.5rem);
    font-weight: 550;
    color: #f3f4f6;
    font-style: italic;
    margin-top: -0.125rem;
    margin-left: 40%;
    letter-spacing: 0.025em;
    line-height: 1.2;
    text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.8), 0 0 15px rgba(0, 0, 0, 0.5);
    white-space: nowrap;
  }

  .hamburger-btn {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    width: 24px;
    height: 18px;
    background: transparent;
    border: none;
    cursor: pointer;
    padding: 0;
    z-index: 1001;
  }

  .hamburger-btn span {
    display: block;
    height: 2px;
    width: 100%;
    background: #ffffff;
    border-radius: 1px;
    transition: all 0.3s ease;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.5);
  }

  .hamburger-btn.active span:nth-child(1) {
    transform: rotate(45deg) translate(5px, 5px);
  }

  .hamburger-btn.active span:nth-child(2) {
    opacity: 0;
  }

  .hamburger-btn.active span:nth-child(3) {
    transform: rotate(-45deg) translate(7px, -6px);
  }

  .mobile-menu-overlay {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    z-index: 998;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s ease;
  }

  .mobile-menu-overlay.open {
    opacity: 1;
    pointer-events: auto;
  }

  .mobile-menu {
    display: none;
    position: fixed;
    top: 0;
    right: -300px;
    width: 280px;
    height: 100%;
    background: rgba(0, 0, 0, 0.85);
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    z-index: 999;
    transition: right 0.3s ease;
    box-shadow: -5px 0 25px rgba(0, 0, 0, 0.5);
    border-left: 1px solid rgba(255, 255, 255, 0.1);
  }

  .mobile-menu.open {
    right: 0;
  }

  .mobile-menu-content {
    padding: 80px 2rem 2rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .mobile-nav-item {
    background: transparent;
    border: 1px solid rgba(255, 255, 255, 0.2);
    color: #ffffff;
    padding: 1rem 1.5rem;
    border-radius: 0.75rem;
    font-size: 1rem;
    font-weight: 600;
    font-family: 'Linden Hill', serif;
    cursor: pointer;
    transition: all 0.3s ease;
    text-align: left;
    width: 100%;
  }

  .mobile-nav-item:hover {
    background: rgba(255, 255, 255, 0.1);
    border-color: rgba(255, 255, 255, 0.4);
    color: #ffffff;
  }

  .mobile-nav-item.active {
    background: rgba(255, 255, 255, 0.15);
    color: #ffffff;
    border-color: rgba(255, 255, 255, 0.4);
    box-shadow: 0 2px 8px rgba(255, 255, 255, 0.1);
    font-weight: 700;
  }

  .pill-bar {
    position: fixed;
    top: 0;
    left: 0;
    background: transparent;
    z-index: 999;
    font-family: 'Linden Hill', serif;
    margin-top: 120px;
    width: auto;
    padding-left: 1.5rem;
    pointer-events: none;
  }

  .desktop-only {
    display: block;
  }

  .pill-container {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 0.75rem;
    padding: 1rem 0;
    width: auto;
    pointer-events: auto;
  }

  .nav-pill {
    background: rgba(255, 255, 255, 0.9);
    border: 1px solid rgba(255, 255, 255, 0.5);
    color: #1f2937;
    padding: 0.5rem 1.25rem;
    border-radius: 2rem;
    font-size: clamp(0.75rem, 2vw, 0.875rem);
    font-weight: 600;
    font-family: 'Linden Hill', serif;
    cursor: pointer;
    transition: all 0.3s ease;
    white-space: nowrap;
    outline: none;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
    width: fit-content;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
  }

  .nav-pill:hover {
    background: rgba(255, 255, 255, 1);
    border-color: rgba(31, 41, 55, 0.6);
    color: #111827;
    transform: translateX(5px);
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
  }

  .nav-pill.active {
    background: rgba(255, 255, 255, 1);
    color: #111827;
    border-color: rgba(31, 41, 55, 0.6);
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
    font-weight: 700;
  }

  .main-content {
    margin-top: 80px;
    margin-left: 0;
    font-family: 'Linden Hill', serif;
    min-height: calc(100vh - 80px);
    background: transparent;
  }

  .content-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem 1.5rem;
    padding-left: 1.5rem;
    padding-right: 1.5rem;
    margin-left: 3%;
  }

  .hero-section {
    text-align: center;
    margin-bottom: 4rem;
    padding: 2rem 0;
    background: rgba(0, 0, 0, 0.2);
    backdrop-filter: blur(5px);
    border-radius: 1rem;
  }

  .hero-section h1 {
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 900;
    color: #ffffff;
    margin-bottom: 1rem;
    line-height: 1.2;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.8), 0 0 25px rgba(0, 0, 0, 0.6);
  }

  .hero-description {
    font-size: clamp(1rem, 2.5vw, 1.25rem);
    color: #f3f4f6;
    max-width: 800px;
    margin: 0 auto;
    line-height: 1.6;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8), 0 0 20px rgba(0, 0, 0, 0.5);
    background: transparent;
    padding: 1rem;
    border-radius: 0.5rem;
    font-weight: 600;
  }

  .portfolio-section {
    margin-bottom: 4rem;
  }

  .portfolio-section h2 {
    font-size: clamp(1.75rem, 4vw, 2.5rem);
    color: #ffffff;
    text-align: center;
    margin-bottom: 2rem;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.8), 0 0 25px rgba(0, 0, 0, 0.6);
    font-weight: 800;
    background: transparent;
    padding: 1rem;
    border-radius: 0.5rem;
  }

  .image-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    margin-bottom: 2rem;
  }

  .image-item {
    border-radius: 1rem;
    overflow: hidden;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
    transition: transform 0.3s ease;
    background: #f8f9fa;
  }

  .image-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
  }

  .image-item img {
    width: 100%;
    height: 250px;
    object-fit: cover;
    display: block;
  }

  .timeline-section h2 {
    font-size: clamp(1.75rem, 4vw, 2.5rem);
    color: #ffffff;
    text-align: center;
    margin-bottom: 3rem;
    text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.8), 0 0 25px rgba(0, 0, 0, 0.6);
    font-weight: 800;
    background: rgba(0, 0, 0, 0.2);
    padding: 1rem;
    border-radius: 0.5rem;
    backdrop-filter: blur(3px);
    -webkit-backdrop-filter: blur(3px);
  }

  .timeline {
    position: relative;
    max-width: 800px;
    margin: 0 auto;
  }

  .timeline::before {
    content: '';
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 3px;
    background: rgba(255, 255, 255, 0.7);
    transform: translateX(-50%);
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  }

  .timeline-item {
    position: relative;
    display: flex;
    align-items: center;
    margin-bottom: 3rem;
  }

  .timeline-item:nth-child(odd) {
    flex-direction: row;
  }

  .timeline-item:nth-child(even) {
    flex-direction: row-reverse;
  }

  .timeline-year {
    background: #1f2937;
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 2rem;
    font-weight: 700;
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    z-index: 10;
    font-size: clamp(0.875rem, 2vw, 1rem);
    white-space: nowrap;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
    border: 2px solid #ffffff;
  }

  .timeline-content {
    width: 45%;
    padding: 1.5rem;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    border: 1px solid rgba(255, 255, 255, 0.3);
    border-radius: 1rem;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
  }

  .timeline-item:nth-child(odd) .timeline-content {
    margin-right: auto;
    text-align: right;
  }

  .timeline-item:nth-child(even) .timeline-content {
    margin-left: auto;
    text-align: left;
  }

  .timeline-content h3 {
    font-size: clamp(1.125rem, 3vw, 1.5rem);
    color: #111827;
    margin-bottom: 0.5rem;
    line-height: 1.3;
    font-weight: 700;
  }

  .timeline-content p {
    color: #374151;
    line-height: 1.6;
    font-size: clamp(0.875rem, 2vw, 1rem);
    font-weight: 500;
  }

  /* Show hamburger menu and hide desktop pill bar below 1025px */
  @media (max-width: 1024px) {
    .hamburger-btn {
      display: flex;
    }

    .desktop-only {
      display: none;
    }

    .mobile-menu-overlay {
      display: block;
    }

    .mobile-menu {
      display: block;
    }

    .content-container {
      padding-left: 1.5rem;
      padding-right: 1.5rem;
      margin-left: 0;
    }

    .main-content {
      margin-left: 0;
    }
  }

  /* Desktop styles - add space only on larger screens */
  @media (min-width: 1025px) {
    .content-container {
      padding-left: 280px;
      padding-right: 1.5rem;
    }
  }

  /* Mobile styles */
  @media (max-width: 768px) {
    .main-content {
      margin-top: 80px;
    }

    .mobile-menu {
      width: 100%;
      right: -100%;
    }

    .hero-section h1 {
      font-size: clamp(1.5rem, 4vw, 2rem);
    }

    .hero-description {
      font-size: clamp(0.875rem, 2vw, 1rem);
    }

    .portfolio-section h2 {
      font-size: clamp(1.25rem, 3.5vw, 1.75rem);
    }

    .brand-text {
      font-size: clamp(1.75rem, 4.5vw, 2.8rem);
    }
  }

  /* Small mobile styles */
  @media (max-width: 480px) {
    .mobile-menu-content {
      padding: 80px 1.5rem 2rem;
    }

    .content-container {
      padding-left: 1rem;
      padding-right: 1rem;
    }

    .hero-section h1 {
      font-size: clamp(1.25rem, 3.5vw, 1.75rem);
    }

    .hero-description {
      font-size: clamp(0.8rem, 1.8vw, 0.95rem);
    }

    .portfolio-section h2 {
      font-size: clamp(1.1rem, 3vw, 1.5rem);
    }

    .brand-text {
      font-size: clamp(1.6rem, 4.2vw, 2.5rem);
    }
  }

  /* Landscape mobile orientation */
  @media (max-height: 500px) and (orientation: landscape) {
    .hero-section {
      padding: 1rem 0;
      margin-bottom: 2rem;
    }

    .mobile-menu-content {
      padding: 70px 2rem 1rem;
      gap: 0.75rem;
    }

    .mobile-nav-item {
      padding: 0.75rem 1.5rem;
    }
  }

  /* High DPI displays */
  @media (-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi) {
    .nav-pill {
      border-width: 0.5px;
    }
  }

  /* Reduced motion preference */
  @media (prefers-reduced-motion: reduce) {
    .nav-pill,
    .image-item,
    .hamburger-btn span,
    .mobile-menu {
      transition: none;
    }
  }

  /* Dark mode support */
  @media (prefers-color-scheme: dark) {
    .navbar {
      background: transparent !important;
    }
    
    .pill-bar {
      background: transparent;
    }
  }

  /* Additional responsive fixes for brand caption */
  @media (max-width: 860px) {
    .brand-caption {
      font-size: clamp(0.9rem, 2.2vw, 1.2rem);
      margin-left: 30%;
    }
  }

  @media (max-width: 650px) {
    .brand-caption {
      font-size: clamp(1.2rem, 2vw, 1.1rem);
      margin-left: 30%;
    }
  }

  @media (max-width: 480px) {
    .brand-caption {
      font-size: clamp(1.2rem, 1.8vw, 1rem);
      margin-left: 30%;
    }
  }
</style>