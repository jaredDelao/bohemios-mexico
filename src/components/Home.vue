<script setup>
import { ref } from 'vue'
import { register } from 'swiper/element/bundle';
import Navbar from './Navbar.vue'
import 'swiper/element/css/pagination'
import 'swiper/element/css/autoplay'
register()
const textIdx = ref(0);

const onSlideChange = (e) => {
  textIdx.value = e.detail[0].snapIndex
}
</script>

<template>
  <Navbar/>
  <div class="content" id="inicio">
    <div class="text-content" v-if="textIdx === 0">
      <h4 class="subtitle">LOS MEJORES MÚSICOS <br> DE MÉXICO.</h4>
      <p>Contratación de:</p>
      <p>Tríos, Duetos, Cuartetos, <br> Solístas y mucho más...</p>
    </div>

    <div class="text-content" style="top: 70%" v-if="textIdx === 1">
      <h4 class="subtitle" style="text-align: right">DISPONIBILIDAD</h4>
      <p style="text-align: right">Las 24 horas.</p>
      <p style="text-align: right">7 días de la semana,</p>
      <p style="text-align: right">Los 365 días del año.</p>
    </div>

    <div class="text-content" v-if="textIdx === 2">
      <h4 class="subtitle" style="text-align: center">CALIDAD Y PRESTIGIO</h4>
      <p style="text-align: center">Nos respalda una tradición</p>
      <p style="text-align: center">de más de 50 años.</p>
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

.content .text-content .subtitle {
  font-size: 3.5em;
  font-weight: 300;
  text-align: left;
  line-height: 1em;
  margin-bottom: 30px;
}
.content .text-content p {
  margin-top: 30px;
  font-size: 2.8em;
  font-weight: 200;
  text-align: left;
  margin: 0px;
  line-height: 1em;
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
