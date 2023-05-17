<template>
  <div class="wrapper" id="galeria">
    <p class="title">GALERIA</p>

    <lightgallery :settings="settings" class="md">
      <a v-for="im in images" :key="im" data-lg-size="1406-1390" class="gallery-item"
        :data-src="'/assets/gallery/'+ im +'.jpeg'"
        >
        <img class="img-responsive" :src="'/assets/gallery/'+ im +'.jpeg'" />
      </a>
    </lightgallery>

    <carousel :items-to-show="1" class="carousel-wrap xs">
      <slide v-for="im in images" :key="im">
        <div class="wrapper-slide">
          <!-- <img src="../assets/gallery/1.jpeg" style="width: 100%"> -->
          <img :src="'/assets/gallery/'+ im +'.jpeg'" style="width: 100%"  class="img-responsive">
        </div>
      </slide>
      <template #addons>
        <navigation>
          <template #prev>
            <span>
              <svg xmlns="http://www.w3.org/2000/svg" height="48" viewBox="0 96 960 960" width="48">
                <path fill="#fff" d="M400 976 0 576l400-400 56 57-343 343 343 343-56 57Z" />
              </svg>
            </span>
          </template>
          <template #next>
            <span><svg xmlns="http://www.w3.org/2000/svg" height="48" viewBox="0 96 960 960" width="48">
                <path fill="#fff" d="m304 974-56-57 343-343-343-343 56-57 400 400-400 400Z" />
              </svg></span>
          </template>
        </navigation>
      </template>
    </carousel>

  </div>
</template>

<script>
import Lightgallery from 'lightgallery/vue';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'

// import 'lightgallery/css/lightgallery.css';

export default {
  name: 'Gallery',
  components: {
    Lightgallery,
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      images: [...Array(21).keys()].slice(1),
      settings: {
        speed: 500,
        controls: true,
        enableDrag: true,
        download: false,
        showCloseIcon: true,
        thumbnail: true,
        prevHtml: `<svg xmlns="http://www.w3.org/2000/svg" height="48" viewBox="0 96 960 960" width="48">
          <path fill="#fff" d="M400 976 0 576l400-400 56 57-343 343 343 343-56 57Z" />
        </svg> `,
        nextHtml: `
        <svg xmlns="http://www.w3.org/2000/svg" height="48" viewBox="0 96 960 960" width="48">
                <path fill="#fff" d="m304 974-56-57 343-343-343-343 56-57 400 400-400 400Z" />
              </svg>
              `
      }
    }
  },
  methods: {
    onInit: () => {
      console.log('lightGallery has been initialized');
    },
    onBeforeSlide: () => {
      console.log('calling before slide');
    },
  },
}
</script>

<style scoped>
.gallery-item {
  margin: 5px;
}

.gallery-item img {
  max-width: 350px;
}


.wrapper {
  background: #000;
  text-align: center;
  padding: 20px 0;
}
.wrapper .title {
  font-size: 6em;
  font-weight: 100;
  color: #fff;
  margin-bottom: 20px !important;
}

@media screen and (max-width: 800px) {
  .wrapper .title {
    font-size: 2.5em;
  }
  .gallery-item img {
    max-width: 300px;
    width: 100%;
  }
}

@media screen and (max-width: 1050px) {
  .wrapper .title {
    font-size: 4em;
  }
}

.xs {
  display: none;
}

@media screen and (max-width: 700px) {
  .md {
    display: none;
  }
  .xs {
    display: block;
  }
  
}
</style>
