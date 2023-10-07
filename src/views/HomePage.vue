<script setup>
import NavBar from '../components/NavBar.vue';
import HeroBar from '../components/HeroBar.vue';
import MainContent from '../components/MainContent.vue';
import FooterBar from '../components/FooterBar.vue';
</script>

<template>
  <NavBar />
  <transition name="fade" appear>
    <HeroBar />
  </transition>
  <transition name="fade" appear>
    <MainContent />
  </transition>
  <transition name="fade" appear>
    <FooterBar />
  </transition>
</template>

<style scoped></style>
