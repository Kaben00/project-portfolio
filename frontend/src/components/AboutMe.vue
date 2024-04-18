<template>
  <v-container class="fill-height">
    <v-row justify="center">
      <v-col cols="12" md="8">
        <div class="about-us">
          <div class="text-h2 about-title">ABOUT</div>
          <div class="about-us-description">
            <div class="about-us-image-container" v-for="(item, index) in aboutUsItems" :key="index">
              <v-avatar size="350"  rounded="0">
                <v-img :src="item.aboutUsImageUrl" height="400px"></v-img>
              </v-avatar>
            </div>
            <div>
              <p class="text-body-1 about-description" v-for="(description, index) in descriptions" :key="index">
                {{ description }}
              </p>
              <div class="text-content" v-for="(item, index) in aboutUsItems" :key="index">
              <div class="about-us-information">
                <h3>{{ item.aboutUsJobTitle }}</h3>
                <p v-for="(value, key) in item.aboutUsDetails" :key="`detail-${key}-${index}`">
                  <b><v-icon large left class="mr-2 arrow-icon">mdi-arrow-right</v-icon>{{ key }}</b> : {{ value }}
                </p>
              </div>
            </div>
          </div>
            
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    descriptions: [],
    aboutUsItems: [
      {
        id: 1,
        aboutUsImageUrl: '/src/assets/images/about-us-image.webp',
        aboutUsJobTitle: 'Frontend and WordPress Developer',
        aboutUsDetails: {
          'Email' : 'kahbengl@hotmail.com',
          'Phone' : '0163537129',
          'City' : 'Kuala Lumpur',
          'Degree' : 'E-Commerce'
        },
      }
    ],
  }),

  mounted() {
    this.fetchDescriptions()
  },

  methods: {
    async fetchDescriptions() {
       const descriptionData = [
        'As a front-end developer, I thrive on the challenges that span from design to development. Like many, I seek fulfillment and growth in my professional endeavors, aspiring to take on greater responsibilities and more complex challenges.',
        'In my current role, I am exposed to a broad spectrum of tasks that have significantly enhanced my coding abilities. These tasks align with the rapidly evolving industry standards and include writing flexible, maintainable, and agnostic code.',
        'I am eager for a position that consistently challenges me, pushes me beyond my comfort zone, and provides opportunities to acquire new skills that will expedite my career progression.'
       ]
       this.descriptions = descriptionData
    }
  },

};
</script>

<style scoped>
  .about-us {
    color: black;
  }

  .about-us-description {
    display: flex;
    align-items: flex-start;
    justify-content: center;
  }

  .about-title {
    text-align: center;
  }

  .about-description {
    text-align: left;
    margin-bottom: 16px;
  }

  .about-us-information h3 {
    color: black;
    font-size: 26px;
  }

  .about-us-information p {
    color: black;
  }

  .about-us-image-container, .text-content {
    padding: 0 15px;
  }

  .about-us-details {
    display: flex;
    align-items: flex-start;
    justify-content: center;
  }

  .arrow-icon {
    color: #0563bb;
  }
</style>
