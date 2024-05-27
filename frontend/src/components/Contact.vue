<template>
  <v-container class="fill-height">
    <v-row justify="center">
      <v-col cols="12" md="8">
        <div class="about-us-description">
          <!-- TODO: MAKE REFERENCE ON LATER DATE -->
          <div class="section-h2-title">REFERENCE</div>
          <div>
            <div class="col-item-6">
              <contact-us-details/>
            </div>
            <div class="col-item-6"></div>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ContactUsDetails from './ContactUsComponents/ContactUsDetails.vue';
export default {
  components: { ContactUsDetails },
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
