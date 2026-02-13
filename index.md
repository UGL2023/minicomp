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

<style>
/* Carousel Container */
.carousel {
  width: 100%;
  max-width: 800px;
  margin: 40px auto;
  overflow: hidden;
  position: relative;
  border-radius: 10px;
}

/* Slides */
.carousel-inner {
  display: flex;
  width: 300%;
  animation: slide 12s infinite;
}

/* Each Slide */
.carousel-item {
  width: 100%;
  flex-shrink: 0;
}

.carousel-item img {
  width: 100%;
  height: 400px;
  object-fit: cover;
  display: block;
}

/* Animation */
@keyframes slide {
  0%   { transform: translateX(0%); }
  33%  { transform: translateX(0%); }

  38%  { transform: translateX(-100%); }
  66%  { transform: translateX(-100%); }

  71%  { transform: translateX(-200%); }
  100% { transform: translateX(-200%); }
}
</style>


<div class="carousel">

  <div class="carousel-inner">

    <div class="carousel-item">
      <img src="/assets/images/1.jpg" alt= 1">
    </div>

    <div class="carousel-item">
      <img src="/assets/images/2.png" alt=" 2">
    </div>

    <div class="carousel-item">
      <img src="/assets/images/3.jpg" alt=" 3">
    </div>

  </div>

</div>
 