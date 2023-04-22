<script setup>
import { onMounted, ref, onUnmounted } from 'vue'
import { register } from 'swiper/element/bundle';
import Navbar from './Navbar.vue'
import 'swiper/element/css/pagination'
import 'swiper/element/css/autoplay'
register()
const spaceBetween = ref(10);
</script>

<template>
  <Navbar/>
  <div class="content">
    <div class="text-content">
      <h4 class="title">BIENVENIDOS</h4>
      <h4 class="subtitle">Tríos, Duetos, Cuartetos, Solistas y más...</h4>
      <p>LA CALIDAD Y EL PRESTIGIO NOS CARACTERIZA</p>
    </div>
    <swiper-container :slides-per-view="1" :autoplay="true" :space-between="spaceBetween" :centered-slides="true"
      :pagination="{
          hideOnClick: true
        }" @slidechange="onSlideChange">
      <swiper-slide>
        <img class="img-slide" src="../assets/carousel/slide1.jpeg">
      </swiper-slide>
      <swiper-slide>
        <img class="img-slide" src="../assets/carousel/slide2.jpeg">
      </swiper-slide>
      <swiper-slide>
        <img class="img-slide" src="../assets/carousel/slide3.jpeg">
      </swiper-slide>
    </swiper-container>
  </div>
</template>

<style scoped>
.content {
  width: 100%;
  height: 100vh;
  background-color: rgba(59, 35, 20, 0.5);
  position: relative;
}

.content .text-content {
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 8;
  text-align: center;
  color: white;
  width: 90%;
}

.content .text-content .title {
  font-size: 6em;
  font-weight: 500;
  line-height: 100px;
}
.content .text-content .subtitle {
  font-size: 3em;
  font-weight: 500;
}
.content .text-content p {
  margin-top: 10%;
  font-size: 2.5em;
  font-weight: 200;
}

swiper-container {
  height: 100%;
}

.img-slide {
  object-fit: cover;
  width: 100%;
  height: 100%;
  filter: brightness(70%);
}

@media screen and (max-width: 800px) {
  .content .text-content .title {
    font-size: 3em;
    font-weight: 700;
  }
  .content .text-content .subtitle {
    font-size: 2.2em;
  }
  .content .text-content p {
    font-size: 2.2em;
  }
}
</style>
