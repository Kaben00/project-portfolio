<template>
 <v-navigation-drawer app permanent class="nav-menu">
    <v-list dense>
        <v-list-item link href="#home" class="nav-item">
          <v-list-item-content class="nav-content">
            <v-icon class="nav-icon">mdi-home</v-icon>
            <v-list-item-title class="nav-title">Home</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link href="#about" class="nav-item">
          <v-list-item-content class="nav-content">
            <v-icon class="nav-icon">mdi-account</v-icon>
            <v-list-item-title class="nav-title">About</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link href="#contact" class="nav-item">
          <v-list-item-content class="nav-content">
            <v-icon class="nav-icon">mdi-email</v-icon>
            <v-list-item-title class="nav-title">Contact</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data: () => ({
  }),

  mounted() {
  },

  methods: {
    scrollToSection(event) {
      const hash = event.currentTarget.hash;
      if (hash) {
        event.preventDefault();
        const section = document.querySelector(hash);
        if (section) {
          section.scrollIntoView({ behavior: 'smooth' });
        }
      }
    },
    
    hoverOverToShowTabName() {

    },
  },
};
</script>

<style scoped>
.nav-menu {
  background: none;
  border-right: none;
  width: 150px !important;
  text-align: center;
}

.v-navigation-drawer__content {
  display: flex;
  align-items: center;
  flex-direction: column;
}

.nav-title {
  display: none;
  margin-left: 10px;
  white-space: nowrap;
}

.nav-content {
  border-radius: 50%;
  background-color: #0563bb;
  width: 50px;
  height: 50px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: width 0.3s ease-in-out;
  overflow: hidden;
}

.nav-item:hover .nav-content {
  width: auto;
  border-radius: 28px;
}

.nav-item:hover .nav-title {
  display: block;
}
</style>
