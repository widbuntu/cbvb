<template>
   <v-app :style="{ backgroundColor: '#e1edf5' }">
    <v-main>
      <Banner />
      <NavBar />
      <br>
      <Carousel />
      <Body />
      <Footer />
    </v-main>
  </v-app>
</template>

<script setup>
import Banner from './components/Banner.vue'
import NavBar from './components/NavBar.vue'
import Carousel from './components/Carousel.vue'
import Body from './components/Body.vue'
import Footer from './components/Footer.vue'
</script>