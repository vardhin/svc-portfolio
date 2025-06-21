<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Linden+Hill:ital@0;1&display=swap" rel="stylesheet">
</svelte:head>

<nav class="navbar">
  <div class="nav-container">
    <!-- Central brand only -->
    <div class="brand">
      <span class="brand-text">Satyam Vision Creators</span>
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
    justify-content: flex-start;
    padding: 1.5rem 2rem;
  }

  .brand {
    display: flex;
    align-items: center;
  }

  .brand-text {
    font-size: 2.5rem;
    font-weight: 900;
    color: #1f2937;
    letter-spacing: -0.025em;
  }

  /* Mobile responsiveness */
  @media (max-width: 768px) {
    .nav-container {
      padding: 1.25rem 1rem;
    }
    
    .brand-text {
      font-size: 2rem;
    }
  }

  @media (max-width: 480px) {
    .brand-text {
      font-size: 1.75rem;
    }
  }
</style>