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
    <!-- TODO: MAKE REFERENCE ON LATER DATE -->
    <section class="footer-section" id="footer">
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

.portfolio-section, .resume-section, .about-me-section {
  height: fit-content;
  background-color: white;
}

.footer-section {
  background-color: #f7f8f9;
}
</style>