<template>
  <div class="app">
    <Header />
    <HeroSection />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import HeroSection from "./components/HeroSection.vue";
//import Footer from "./components/Footer.vue"

export default {
  components: { Header, HeroSection },
};
</script>

<style>
body {
  margin: 0;
  font-family: "neue-haas-grotesk-display", sans-serif;
  background-color: var(--color-background);
}
</style>
