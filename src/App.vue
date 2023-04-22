<script setup>
import HelloWorld from './components/HelloWorld.vue'
import AboutUs from './components/AboutUs.vue'
import Home from './components/Home.vue'
import Services from './components/Services.vue'
import MeetUs from './components/MeetUs.vue'

</script>

<template>
  <div class="content">
    <Home />
    <AboutUs />
    <Services />
    <MeetUs />
  </div>
</template>

<style scoped>
  .content {
    width: 100%;
  }
</style>
