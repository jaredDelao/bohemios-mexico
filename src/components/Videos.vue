<template>
  <div class="videos">
    <span class="title">VIDEOS</span>
    <carousel :items-to-show="1" class="carousel-wrap">
      <slide v-for="video in iframes" :key="video">
        <div class="wrapper-slide">
          <iframe height="100%" width="100vw" :src="video" frameborder="0" title="YouTube video player"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen></iframe>
        </div>
      </slide>
      <template #addons>
        <navigation>
          <template #prev>
            <span>
              <svg xmlns="http://www.w3.org/2000/svg" height="48" viewBox="0 96 960 960" width="48">
                <path fill="#111" d="M400 976 0 576l400-400 56 57-343 343 343 343-56 57Z" />
              </svg>
            </span>
          </template>
          <template #next>
            <span><svg xmlns="http://www.w3.org/2000/svg" height="48" viewBox="0 96 960 960" width="48">
                <path fill="#111" d="m304 974-56-57 343-343-343-343 56-57 400 400-400 400Z" />
              </svg></span>
          </template>
        </navigation>
      </template>
    </carousel>
  </div>
</template>

<script>
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'

export default {
  name: 'Videos',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      iframes: [
        'https://www.youtube-nocookie.com/embed/aNTZ20gBff8',
        'https://www.youtube-nocookie.com/embed/oFXZfhpHLtQ',
        'https://www.youtube-nocookie.com/embed/5qbsr-Sr3iE',
        'https://www.youtube-nocookie.com/embed/CyWzmz7KqPk'
      ]
    }
  }
}
</script>

<style scoped>
.carousel-wrap,
.videos {
  text-align: center;
  background: var(--secondary);
  padding: 20px 0;
}

.videos .title {
  font-size: 6em;
  font-weight: 100;
  color: #111;
}

.wrapper-slide {
  height: 80vh;
  width: 80%;
  margin: auto;
}

iframe {
  width: 100%;
}

.carousel__icon {
  fill: red !important;
}

@media screen and (max-width: 800px) {
  .videos .title {
    font-size: 2.5em;
  }
}

@media screen and (max-width: 1050px) {
  .videos .title {
    font-size: 4em;
  }
}
</style>
