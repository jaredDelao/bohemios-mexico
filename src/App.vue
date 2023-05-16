<script setup>
import AboutUs from './components/AboutUs.vue'
import Home from './components/Home.vue'
import Services from './components/Services.vue'
import MeetUs from './components/MeetUs.vue'
import Videos from './components/Videos.vue'
import Gallery from './components/Gallery.vue'
import Contact from './components/Contact.vue'

</script>

<template>
  <div class="content">
    <Home />
    <AboutUs />
    <Services />
    <MeetUs />
    <Videos />
    <Gallery />
    <Contact />
  </div>
</template>

<style scoped>
  .content {
    width: 100%;
  }
</style>
