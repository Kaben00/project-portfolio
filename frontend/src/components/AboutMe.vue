<template>
  <v-container class="fill-height">
    <v-row justify="center">
      <v-col cols="12" md="8">
        <div class="about-us-description">
          <div class="text-h2 about-title">About</div>
          <p class="text-body-1 about-description">I am Kah Beng. An avid developer love all about programming.</p>
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

  .about-title, .about-description {
    text-align: center;
  }
</style>
