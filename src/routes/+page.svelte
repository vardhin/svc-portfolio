<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Linden+Hill:ital@0;1&display=swap" rel="stylesheet">
</svelte:head>

<script>
  let activeSection = 'interior-design'; // Default active section

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
  </div>
</nav>

<!-- Secondary pill bar -->
<div class="pill-bar">
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

  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    z-index: 1000;
    font-family: 'Linden Hill', serif;
    min-height: 80px;
  }

  .nav-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding: 1rem 1.5rem;
    min-height: 80px;
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
    color: #1f2937;
    letter-spacing: -0.025em;
    line-height: 1.1;
  }

  .brand-caption {
    font-size: clamp(1rem, 2.5vw, 1.25rem);
    font-weight: 550;
    color: #26282c;
    font-style: italic;
    margin-top: -0.125rem;
    letter-spacing: 0.025em;
    line-height: 1.2;
  }

  .pill-bar {
    position: fixed;
    top: 80px;
    left: 0;
    right: 0;
    background: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(0, 0, 0, 0.05);
    z-index: 999;
    font-family: 'Linden Hill', serif;
    min-height: 60px;
  }

  .pill-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    gap: 0.5rem;
    padding: 1rem 1.5rem;
    flex-wrap: wrap;
    min-height: 60px;
    align-items: center;
  }

  .nav-pill {
    background: transparent;
    border: 1px solid rgba(107, 114, 128, 0.3);
    color: #6b7280;
    padding: 0.5rem 1.25rem;
    border-radius: 2rem;
    font-size: clamp(0.75rem, 2vw, 0.875rem);
    font-weight: 500;
    font-family: 'Linden Hill', serif;
    cursor: pointer;
    transition: all 0.3s ease;
    white-space: nowrap;
    outline: none;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
  }

  .nav-pill:hover {
    background: rgba(31, 41, 55, 0.05);
    border-color: rgba(31, 41, 55, 0.4);
    color: #374151;
    transform: translateY(-1px);
  }

  .nav-pill.active {
    background: #1f2937;
    color: white;
    border-color: #1f2937;
    box-shadow: 0 2px 8px rgba(31, 41, 55, 0.2);
  }

  .main-content {
    margin-top: 140px;
    font-family: 'Linden Hill', serif;
    min-height: calc(100vh - 140px);
  }

  .content-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem 1.5rem;
  }

  .hero-section {
    text-align: center;
    margin-bottom: 4rem;
    padding: 2rem 0;
  }

  .hero-section h1 {
    font-size: clamp(2rem, 5vw, 3rem);
    font-weight: 900;
    color: #1f2937;
    margin-bottom: 1rem;
    line-height: 1.2;
  }

  .hero-description {
    font-size: clamp(1rem, 2.5vw, 1.25rem);
    color: #6b7280;
    max-width: 800px;
    margin: 0 auto;
    line-height: 1.6;
  }

  .portfolio-section {
    margin-bottom: 4rem;
  }

  .portfolio-section h2 {
    font-size: clamp(1.75rem, 4vw, 2.5rem);
    color: #1f2937;
    text-align: center;
    margin-bottom: 2rem;
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
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
    background: #f8f9fa;
  }

  .image-item:hover {
    transform: translateY(-5px);
  }

  .image-item img {
    width: 100%;
    height: 250px;
    object-fit: cover;
    display: block;
  }

  .timeline-section h2 {
    font-size: clamp(1.75rem, 4vw, 2.5rem);
    color: #1f2937;
    text-align: center;
    margin-bottom: 3rem;
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
    width: 2px;
    background: #e5e7eb;
    transform: translateX(-50%);
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
    font-weight: 600;
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    z-index: 10;
    font-size: clamp(0.875rem, 2vw, 1rem);
    white-space: nowrap;
  }

  .timeline-content {
    width: 45%;
    padding: 1.5rem;
    background: white;
    border-radius: 1rem;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
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
    color: #1f2937;
    margin-bottom: 0.5rem;
    line-height: 1.3;
  }

  .timeline-content p {
    color: #6b7280;
    line-height: 1.6;
    font-size: clamp(0.875rem, 2vw, 1rem);
  }

  /* Tablet styles */
  @media (max-width: 1024px) {
    .content-container {
      padding: 1.5rem 1rem;
    }

    .image-gallery {
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.25rem;
    }

    .nav-container {
      justify-content: center;
    }
  }

  /* Mobile styles */
  @media (max-width: 768px) {
    .navbar {
      min-height: 70px;
    }

    .nav-container {
      padding: 0.75rem 1rem;
      justify-content: center;
      min-height: 70px;
    }

    .pill-bar {
      top: 70px;
      min-height: 80px;
    }

    .pill-container {
      gap: 0.375rem;
      padding: 0.75rem 1rem;
      min-height: 80px;
    }

    .nav-pill {
      padding: 0.4rem 1rem;
      font-size: 0.8125rem;
    }

    .main-content {
      margin-top: 150px;
    }

    .content-container {
      padding: 1rem 1rem;
    }

    .hero-section {
      margin-bottom: 3rem;
      padding: 1rem 0;
    }

    .image-gallery {
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1rem;
    }

    .image-item img {
      height: 200px;
    }

    /* Simplified mobile timeline */
    .timeline::before {
      left: 1rem;
    }

    .timeline-year {
      left: 1rem;
      transform: none;
      position: relative;
      margin-bottom: 1rem;
      display: inline-block;
    }

    .timeline-content {
      width: calc(100% - 2rem);
      margin-left: 2rem !important;
      text-align: left !important;
    }

    .timeline-item {
      flex-direction: column !important;
      align-items: flex-start !important;
    }
  }

  /* Small mobile styles */
  @media (max-width: 480px) {
    .navbar {
      min-height: 60px;
    }

    .nav-container {
      min-height: 60px;
      padding: 0.5rem 0.75rem;
    }

    .pill-bar {
      top: 60px;
      min-height: 100px;
    }

    .pill-container {
      padding: 0.5rem 0.75rem;
      gap: 0.25rem;
      min-height: 100px;
    }

    .nav-pill {
      padding: 0.375rem 0.875rem;
      font-size: 0.75rem;
    }

    .main-content {
      margin-top: 160px;
    }

    .content-container {
      padding: 1rem 0.75rem;
    }

    .image-gallery {
      grid-template-columns: 1fr;
      gap: 1rem;
    }

    .image-item img {
      height: 180px;
    }

    .timeline-content {
      padding: 1rem;
      width: calc(100% - 1rem);
      margin-left: 1rem !important;
    }
  }

  /* Landscape mobile orientation */
  @media (max-height: 500px) and (orientation: landscape) {
    .hero-section {
      padding: 1rem 0;
      margin-bottom: 2rem;
    }
    
    .main-content {
      margin-top: 120px;
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
    .image-item {
      transition: none;
    }
  }

  /* Dark mode support */
  @media (prefers-color-scheme: dark) {
    .navbar {
      background: rgba(31, 41, 55, 0.95);
    }
    
    .pill-bar {
      background: rgba(31, 41, 55, 0.95);
    }
    
    .brand-text {
      color: #f9fafb;
    }
    
    .brand-caption {
      color: #d1d5db;
    }
  }
</style>