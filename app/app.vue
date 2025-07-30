<template>
  <div>
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <div class="swiper-slide">Slide 1</div>
        <div class="swiper-slide">Slide 2</div>
        <div class="swiper-slide">Slide 3</div>
        <div class="swiper-slide">Slide 4</div>
        <div class="swiper-slide">Slide 5</div>
      </div>

      <!-- Navigation buttons -->
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from "vue";
import Swiper from "swiper/bundle";
import "swiper/css/bundle";

onMounted(() => {
  new Swiper(".swiper-container", {
    slidesPerView: 3,
    spaceBetween: 30,
    centeredSlides: true,
    roundLengths: true,
    loop: true,
    pagination: {
      el: ".swiper-pagination",
      clickable: true,
    },
    navigation: {
      nextEl: ".swiper-button-next",
      prevEl: ".swiper-button-prev",
    },
  });
});
</script>

<style scoped>
.swiper-container {
  width: 90vw;
  height: 300px;
  position: relative;
  margin: 2rem auto;
}

.swiper-slide {
  height: 300px;
  background: #eee;
  display: flex;
  align-items: center;
  justify-content: center;
  transform: scale(0.8);
  transition: all 200ms ease-in-out;
}

.swiper-slide.swiper-slide-active {
  transform: scale(1);
  background: #fcbf49;
}
</style>
