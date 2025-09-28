<template>
  <v-container class="fill-height">
    <v-responsive
      class="align-centerfill-height mx-auto hero-image"
    >
      <v-row justify="center">
        <v-col cols="12">
          <div class="homepage">
            <h1 class="text-h1 font-weight-bold home-person-name">Kah Beng</h1>
            <p class="main-text">
              Hi, I am a
              <home-job-scope/>
            </p>
          </div>
        </v-col>
      </v-row>
    </v-responsive>
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
  .v-application {
    background: url('./assets/images/hero-background-image.jpg') !important;
  }

  .main-text {
    font-size: 26px;
    display: flex;
    columns: left;
  }

  .home-person-name {
    line-height: 7rem;
  }
</style>
