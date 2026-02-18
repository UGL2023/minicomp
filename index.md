---
layout: default
title: Home
---

<div markdown="0">

  <!-- ==========================
       Google Font
  ========================== -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap" rel="stylesheet">

  <!-- ==========================
       Header
  ========================== -->
  <header class="site-header">
    <h1 class="scroll-heading">
      <span class="line1">University of Guyana Library</span><br>
      <span class="line2">Digital Collections</span>
    </h1>
  </header>

  <style>
    /* ==========================
       Header
    ========================== */
    .site-header {
      text-align: center;
      margin: 40px 0;
    }

    /* ==========================
       Animated Heading
    ========================== */
    .scroll-heading {
      color: #CC5500;
      font-family: 'Sreda', sans-serif;
      font-weight: 700;
      font-size: clamp(24px, 5vw, 36px);
      margin: 0;
      text-shadow: 2px 2px 6px rgba(204,85,0,0.6);
    }

    .scroll-heading span {
      display: inline-block;
      opacity: 0;
      transform: translateY(-100px);
      animation: slideIn 1s forwards ease-out;
    }

    .scroll-heading .line1 { animation-delay: 0.3s; }
    .scroll-heading .line2 { animation-delay: 1s; }

    @keyframes slideIn {
      0% { opacity: 0; transform: translateY(-100px); }
      80% { transform: translateY(10px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    /* ==========================
       Carousel Styles
    ========================== */
    .carousel {
      max-width: 700px;
      margin: 40px auto;
      overflow: hidden;
      position: relative;
      border-radius: 10px;
      height: clamp(250px, 40vh, 500px);
    }

    .carousel-item {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      opacity: 0;
      transition: opacity 1s ease-in-out;
    }

    .carousel-item.active {
      opacity: 1;
      position: relative;
    }

    .carousel-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
    }

    @media (max-width: 600px) {
      .carousel-item img {
        object-fit: contain;
      }
    }

    /* Carousel Navigation */
    .prev, .next {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: #CC5500;
      color: #fff;
      border: none;
      font-size: 2rem;
      padding: 0.5rem 1rem;
      cursor: pointer;
      border-radius: 5px;
      z-index: 10;
    }
    .prev { left: 10px; }
    .next { right: 10px; }

    /* Carousel Dots */
    .dots {
      position: absolute;
      bottom: 15px;
      width: 100%;
      text-align: center;
      z-index: 10;
    }

    .dot {
      height: 12px;
      width: 12px;
      margin: 0 5px;
      background: #033b03;
      border-radius: 50%;
      display: inline-block;
      cursor: pointer;
      transition: background 0.3s;
    }

    .dot.active { background: #CC5500; }

    /* ==========================
       Library Description
    ========================== */
    .library-text {
      font-family: 'Montserrat', sans-serif;
      font-size: 14px;
      line-height: 1.6;
      color: #000;
      max-width: 1000px;
      margin: 20px auto;
      text-align: justify;
    }
  </style>

  <!-- ==========================
       Carousel HTML
  ========================== -->
  <div class="carousel">
    <div class="carousel-item active">
      <img src="{{ '/assets/images/slide1.jpg' | relative_url }}" alt="Slide 1">
    </div>
    <div class="carousel-item">
      <img src="{{ '/assets/images/slide2.jpg' | relative_url }}" alt="Slide 2">
    </div>
    <div class="carousel-item">
      <img src="{{ '/assets/images/slide3.jpg' | relative_url }}" alt="Slide 3">
    </div>

    <button class="prev" aria-label="Previous Slide">&#10094;</button>
    <button class="next" aria-label="Next Slide">&#10095;</button>

    <div class="dots"></div>
  </div>

  <!-- ==========================
       Carousel Script
  ========================== -->
  <script>
    document.addEventListener("DOMContentLoaded", function () {
      const slides = document.querySelectorAll('.carousel-item');
      const prevBtn = document.querySelector('.prev');
      const nextBtn = document.querySelector('.next');
      const dotsContainer = document.querySelector('.dots');
      let index = 0;

      slides.forEach((_, i) => {
        const dot = document.createElement('span');
        dot.classList.add('dot');
        if (i === 0) dot.classList.add('active');
        dot.addEventListener('click', () => { goToSlide(i); resetTimer(); });
        dotsContainer.appendChild(dot);
      });

      const dots = document.querySelectorAll('.dot');

      function goToSlide(n) {
        if (n < 0) n = slides.length - 1;
        if (n >= slides.length) n = 0;
        slides.forEach(s => s.classList.remove('active'));
        slides[n].classList.add('active');
        dots.forEach(d => d.classList.remove('active'));
        dots[n].classList.add('active');
        index = n;
      }

      function nextSlide() { goToSlide(index + 1); }
      function prevSlide() { goToSlide(index - 1); }

      nextBtn.addEventListener('click', () => { nextSlide(); resetTimer(); });
      prevBtn.addEventListener('click', () => { prevSlide(); resetTimer(); });

      let timer = setInterval(nextSlide, 5000);
      function resetTimer() { clearInterval(timer); timer = setInterval(nextSlide, 5000); }

      // Mobile swipe support
      let startX = 0;
      const carousel = document.querySelector('.carousel');
      carousel.addEventListener('touchstart', e => startX = e.touches[0].clientX);
      carousel.addEventListener('touchend', e => {
        const diff = startX - e.changedTouches[0].clientX;
        if (Math.abs(diff) > 50) diff > 0 ? nextSlide() : prevSlide();
        resetTimer();
      });
    });
  </script>

  <!-- ==========================
       Library Description
  ========================== -->
  <p class="library-text">
    The Library remains committed to serving you, our users, to the improvement of our services and to the improvement of the access and delivery of information.
  </p>
  <p class="library-text">
    We trust that you will find the information on this site interesting. We welcome your comments and suggestions.
  </p>

</div>
