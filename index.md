---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#

layout: default
title: Home
---

<div markdown="0">

<h1 style="color: black; text-align:center;">
University of Guyana Library<br>
Digital Collections</h1>

<div class="carousel">
  <div class="carousel-inner">
    {% assign slides = "/assets/images/slide1.jpg,/assets/images/slide2.jpg,/assets/images/slide3.jpg" | split: "," %}
    {% for slide in slides %}
    <div class="carousel-item {% if forloop.first %}active{% endif %}">
      <img src="{{ slide | relative_url }}" alt="Slide {{ forloop.index }}">
    </div>
    {% endfor %}
  </div>

  <!-- Arrows -->
  <button class="prev">&#10094;</button>
  <button class="next">&#10095;</button>

  <!-- Dots -->
  <div class="dots">
    {% for slide in slides %}
    <span class="dot {% if forloop.first %}active{% endif %}"></span>
    {% endfor %}
  </div>
</div>

<style>
.carousel {
  width: 100%;
  max-width: 800px;
  height: 50vh;
  margin: 40px auto;
  overflow: hidden;
  position: relative;
  border: 0px solid orange;
  border-radius: 0px;
}

.carousel-inner {
  position: relative;
  width: 100%;
  height: 100%;
}

.carousel-item {
  position: absolute;
  top: 0; left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 1s ease-in-out;
}

.carousel-item.active {
  opacity: 1;
}

.carousel-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 5px;
}

/* Arrows */
.prev, .next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0,0,0,0.5);
  color: white;
  border: none;
  font-size: 2rem;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 5px;
  z-index: 10;
}
.prev { left: 10px; }
.next { right: 10px; }

/* Dots */
.dots {
  position: absolute;
  bottom: 15px;
  width: 100%;
  text-align: center;
}
.dot {
  height: 12px;
  width: 12px;
  margin: 0 5px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  cursor: pointer;
}
.dot.active { background-color: #717171; }

/* Responsive */
@media (max-width: 600px) {
  .carousel { height: 30vh; }
  .prev, .next { font-size: 1.5rem; padding: 0.3rem 0.7rem; }
  .dot { height: 10px; width: 10px; }
}
</style>

<script>
const slides = document.querySelectorAll('.carousel-item');
const dots = document.querySelectorAll('.dot');
const prevBtn = document.querySelector('.prev');
const nextBtn = document.querySelector('.next');

let slideIndex = 0;

function showSlide(n) {
  slides.forEach(s => s.classList.remove('active'));
  dots.forEach(d => d.classList.remove('active'));
  slides[n].classList.add('active');
  dots[n].classList.add('active');
  slideIndex = n;
}

function nextSlide() { showSlide((slideIndex + 1) % slides.length); }
function prevSlide() { showSlide((slideIndex - 1 + slides.length) % slides.length); }

// Dots click
dots.forEach((dot,i) => dot.addEventListener('click', () => showSlide(i)));

// Arrows click
nextBtn.addEventListener('click', () => { nextSlide(); resetAutoSlide(); });
prevBtn.addEventListener('click', () => { prevSlide(); resetAutoSlide(); });

// Auto slide
let autoSlide = setInterval(nextSlide, 5000);
function resetAutoSlide() {
  clearInterval(autoSlide);
  autoSlide = setInterval(nextSlide, 5000);
}

// Touch swipe support
let startX = 0, endX = 0;
const threshold = 50;
const carouselEl = document.querySelector('.carousel');

carouselEl.addEventListener('touchstart', e => startX = e.touches[0].clientX);
carouselEl.addEventListener('touchmove', e => endX = e.touches[0].clientX);
carouselEl.addEventListener('touchend', () => {
  let diff = startX - endX;
  if(Math.abs(diff) > threshold){
    diff > 0 ? nextSlide() : prevSlide();
    resetAutoSlide();
  }
});

// Initialize
showSlide(0);
</script>
