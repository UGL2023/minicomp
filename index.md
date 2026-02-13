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
    <div class="carousel-item">
      <img src="{{ '/assets/images/slide1.jpg' | relative_url }}" alt="slide1">
    </div>
    <div class="carousel-item">
      <img src="{{ '/assets/images/slide2.jpg' | relative_url }}" alt="slide2">
    </div>
    <div class="carousel-item">
      <img src="{{ '/assets/images/slide3.jpg' | relative_url }}" alt="slide3">
    </div>
  </div>
</div>

<style>
.carousel {
  width: 800px;
  height: 400px;
  margin: 40px auto;
  overflow: hidden;
  position: relative;
  border: 4px solid red;
}

.carousel-inner {
  position: relative;
  width: 100%;
  height: 100%;
}

.carousel-item {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0;
  transform: translateX(100%);
  animation: slideFade 9s linear infinite;
}

.carousel-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Slide + fade animation */
@keyframes slideFade {
  0%   { opacity: 0; transform: translateX(100%); }
  10%  { opacity: 1; transform: translateX(0%); }
  30%  { opacity: 1; transform: translateX(0%); }
  40%  { opacity: 0; transform: translateX(-100%); }
  100% { opacity: 0; transform: translateX(-100%); }
}

/* stagger animations for each slide */
.carousel-item:nth-child(1) { animation-delay: 0s; }
.carousel-item:nth-child(2) { animation-delay: 3s; }
.carousel-item:nth-child(3) { animation-delay: 6s; }
</style>
