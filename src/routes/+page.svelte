<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Linden+Hill:ital@0;1&display=swap" rel="stylesheet">
</svelte:head>

<nav class="navbar">
  <div class="nav-container">
    <!-- Central brand -->
    <div class="brand">
      <div class="brand-content">
        <span class="brand-text">Satyam Vision Creators</span>
        <span class="brand-caption">we create your dreams</span>
      </div>
    </div>
    
    <!-- Navigation links -->
    <div class="nav-links">
      <a href="#interior-design" class="nav-link">Interior Design</a>
      <a href="#event-organization" class="nav-link">Event Organization</a>
      <a href="#civil-work" class="nav-link">Civil Work</a>
      <a href="#publicity" class="nav-link">Publicity - Ad Service</a>
    </div>
  </div>
</nav>

<style>
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
  }

  .nav-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem 2rem;
  }

  .brand {
    display: flex;
    align-items: center;
  }

  .brand-content {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .brand-text {
    font-size: 2.5rem;
    font-weight: 900;
    color: #1f2937;
    letter-spacing: -0.025em;
  }

  .brand-caption {
    font-size: 1.25rem;
    font-weight: 550;
    color: #26282c;
    font-style: italic;
    margin-top: 0.25rem;
    margin-left: 0.15rem;
    letter-spacing: 0.025em;
    align-self: flex-end;
  }

  .nav-links {
    display: flex;
    gap: 2rem;
    align-items: center;
  }

  .nav-link {
    color: #374151;
    text-decoration: none;
    font-weight: 500;
    font-size: 1.125rem;
    transition: color 0.2s ease;
    white-space: nowrap;
  }

  .nav-link:hover {
    color: #1f2937;
  }

  /* Mobile responsiveness */
  @media (max-width: 768px) {
    .nav-container {
      padding: 0.75rem 1rem;
    }
    
    .brand-text {
      font-size: 2rem;
    }

    .brand-caption {
      font-size: 1.125rem;
    }

    .nav-links {
      display: none;
    }
  }

  @media (max-width: 480px) {
    .brand-text {
      font-size: 1.75rem;
    }

    .brand-caption {
      font-size: 2rem;
    }
  }
</style>