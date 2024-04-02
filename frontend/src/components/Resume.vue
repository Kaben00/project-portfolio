<template>
  <v-container class="fill-height">
    <v-row justify="center">
      <v-col cols="12" md="8">
        <div class="about-us-description">
          <div class="text-h2 section-title">Resume</div>
          <p class="text-body-1 section-description">A professional frontend developer.</p>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import HomeJobScope from './HomeComponents/HomeJobScope.vue';
export default {
  components: { HomeJobScope },
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
