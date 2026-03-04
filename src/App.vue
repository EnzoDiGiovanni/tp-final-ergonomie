<script setup>
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue";
import HeroSection from "./components/HeroSection.vue";
import ContentSections from "./components/ContentSections.vue";
</script>

<template>
  <div id="app">
    <Header />

    <main id="main-content">
      <HeroSection />
      <ContentSections />
    </main>

    <Footer />
  </div>
</template>
