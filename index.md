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

<h1 style="color: orange; text-align:center;">
University of Guyana Library Digital Collections
</h1>

<style>
.carousel {
  width: 800px;
  height: 400px;
  margin: 40px auto;
  overflow: hidden;
  border: 4px solid red;
}

.carousel-inner {
  display: flex;
  width: 300%;
  height: 100%;
  animation: slide 9s infinite;
}

.carousel-item {
  width: 100%;
  height: 100%;
  flex-shrink: 0;
}

.carousel-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
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
      <img src="{{ site.baseurl }}/assets/images/slide1.jpg">
    </div>

    <div class="carousel-item">
      <img src="{{ site.baseurl }}/assets/images/slide2.jpg">
    </div>

    <div class="carousel-item">
      <img src="{{ site.baseurl }}/assets/images/slide3.jpg">
    </div>

  </div>

</div>

</div>
