<template>
  <v-container class="fill-height">
    <v-row justify="center">
      <v-col cols="12" md="8">
        <div class="about-us-description">
          <div class="text-h2 section-title">PORTFOLIO</div>
          <p class="text-body-1 section-description">Here is the portfolios that I have accomplished over the course of my career.</p>
          <PortfolioProject/>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import PortfolioProject from './PortfolioComponents/PortfolioProject.vue';

export default {
  data: () => ({
  }),

  mounted() {
  },

  methods: {
  },
};
</script>

<style scoped>
  .about-us-description {
    color: black;
  }
</style>
