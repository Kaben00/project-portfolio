<template>
  <v-container app class="footer-container">
    <div class="footer-items">
      <h3 class="h3-title">Kah Beng</h3>
      <div
        class="footer-caption"
      >
      {{ (new Date()).getFullYear() }} - <span class="d-sm-inline-block">A Website by Kah Beng</span>
      </div>
      <!-- TODO: ADD SOCIAL MEDIA LINK AND ICON -->
      <!-- <a
        v-for="item in items"
        :key="item.title"
        :href="item.href"
        :title="item.title"
        class="d-inline-block mx-2 social-link"
        rel="noopener noreferrer"
        target="_blank"
      >
        <v-icon
          :icon="item.icon"
          :size="item.icon === '$vuetify' ? 24 : 16"
        />
      </a> -->
      
    </div>
  </v-container>
</template>

<script setup>
  const items = [
    {
      title: 'GitHub',
      icon: `mdi-github`,
      href: 'https://github.com/vuetifyjs/vuetify',
    },
  ]
</script>

<style scoped>
  .footer-container {
    position: relative !important;
    color: black;
    background-color: #f7f8f9;
    justify-content: center;
    text-align: center;
  }

  .text-caption {
    text-align: center;
  }

  .footer-items {
    display: flex;
    flex-direction: column;
  }

  .footer-caption {
    align-items: end;
  }
</style>