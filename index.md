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
<h1 style="orange">University of Guyana Library Digital Collections</h1>

<div markdown="0">

<style>
.carousel {
  width: 100%;
  max-width: 800px;
  margin: 40px auto;
  overflow: hidden;
  position: relative;
  border-radius: 10px;
}

.carousel-inner {
  display: flex;
  width: 300%;
  animation: slide 12s infinite;
}

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

@keyframes slide {
  0%,33%   { transform: translateX(0%); }
  38%,66%  { transform: translateX(-100%); }
  71%,100% { transform: translateX(-200%); }
}
</style>


<div class="carousel">

  <div class="carousel-inner">

    <div class="carousel-item">
      <img src="{{ '/assets/images/slide1.jpg' | relative_url }}" alt="Slide 1">
    </div>

    <div class="carousel-item">
      <img src="{{ '/assets/images/slide2.jpg' | relative_url }}" alt="Slide 2">
    </div>

    <div class="carousel-item">
      <img src="{{ '/assets/images/slide3.jpg' | relative_url }}" alt="Slide 3">
    </div>

  </div>

</div>

</div>
