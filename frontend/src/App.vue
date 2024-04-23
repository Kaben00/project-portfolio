<template>
  <v-app>
    <nav-menu/>
    <section class="home-section" id="home">
      <Home />
    </section >
    <section class="about-me-section" id="about">
      <about-me/>
    </section >
    <section class="resume-section" id="resume">
      <resume/>
    </section >
    <section class="portfolio-section" id="portfolio">
      <portfolio/>
    </section >
    <section class="contact-section" id="contact">
      <contact/>
    </section >
    <section>
      <Footer/>
    </section>

  </v-app>
</template>

<script setup>
  //
</script>

<style scoped>
.home-section {
  background: url('./assets/images/hero-background-image.jpg') !important;
  background-repeat: no-repeat;
  background-size: cover !important;
  height: 100vh;
}

.about-me-section, .resume-section, .portfolio-section, .contact-section {
  height: 100vh;
  background-color: white;
}
</style>