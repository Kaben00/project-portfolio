<template>
  <v-container>
    <v-list lines="one" theme="white">
      <v-list-item 
        v-for="item in contactUsItems"
        :key="item.id"
        link>
          <v-list-item-content class="contact-content">
            <v-icon class="contact-icon">{{ item.icon }}</v-icon>
            <div class="contact-information">
              <h4 class="contact-h4">{{ item.contactUsItemDetailTitle }}</h4>
              <p class="contact-p">{{ item.contactUsItemDetail }}</p>
            </div>
          </v-list-item-content>
      </v-list-item>
      </v-list>
  </v-container>
</template>

<script>
  export default {
    data : () => ({
      contactUsItems: [
    { id: '1', contactUsItemDetailTitle: 'Location', contactUsItemDetail: 'Kuala Lumpur', icon: 'mdi-map-marker' },
    { id: '2', contactUsItemDetailTitle: 'Email', contactUsItemDetail: 'kahbengl@hotmail.com', icon: 'mdi-email-outline' },
    { id: '3', contactUsItemDetailTitle: 'Call', contactUsItemDetail: '+60-16 353 7129', icon: 'mdi-phone-outline' },
  ],
  }),
}
</script>

<style scoped>
  .contact-content {
    display: flex;
    color: black;
  }

  .contact-icon {
    float:left;
    margin-right: 10px;
  }

  .contact-information {
    margin-left: 10px;
  }

  .contact-h4 {
    margin-bottom: 10px;
  }

  .v-list {
    background: rgb(255 255 255) !important;
  }
</style>