<template>
 <v-navigation-drawer app permanent class="nav-menu">
    <v-list dense>
      <!-- TODO: ADD MOBILE RESPONSIVE MENU -->
      <v-list-item 
        v-for="item in menuItems"
        :key="item.id"
        @click.prevent="scrollToSection('#' + item.id)"
        :class="{'nav-item': true, 'active': activeSection === item.id}"
        link>
          <v-list-item-content class="nav-content">
            <v-icon class="nav-icon">{{ item.icon }}</v-icon>
            <v-list-item-title class="nav-title">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
      </v-list-item>
      </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data: () => ({
    activeSection: '',
    menuItems: [
    { id: 'home', title: 'Home', icon: 'mdi-home' },
    { id: 'about', title: 'About', icon: 'mdi-account' },
    { id: 'resume', title: 'Resume', icon: 'mdi-briefcase' },
    { id: 'portfolio', title: 'Portfolio', icon: 'mdi-image' },
    // TODO: MAKE REFERENCE ON LATER DATE
    // { id: 'contact', title: 'Contact', icon: 'mdi-email' }
  ],
  }),

  mounted() {
      const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        this.activeSection = entry.target.id;
      }
    });
  }, { threshold: 0.3 });

  this.menuItems.forEach(item => {
    const el = document.getElementById(item.id);
    if (el) observer.observe(el);
  });
  },

  beforeDestroy() {
    observer.disconnect();
  },

  methods: {
    scrollToSection(selector) {
      const section = document.querySelector(selector);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' });
      }
    },
    
    handleScroll() {
      const sections = ['home', 'about', 'resume', 'portfolio', 'contact'];
      const offsets = sections.map(id => {
        const el = document.getElementById(id);
        return el ? el.getBoundingClientRect().top + window.scrollY : null;
      });

      const currentPosition = window.scrollY + window.innerHeight / 2; // Middle of the viewport
      let closestSection = '';
      let smallestDiff = Infinity;

      offsets.forEach((offset, index) => {
        if (offset !== null && Math.abs(currentPosition - offset) < smallestDiff) {
          smallestDiff = Math.abs(currentPosition - offset);
          closestSection = sections[index];
        }
      });

      this.activeSection = closestSection;
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

.nav-item .nav-content {
  border-radius: 50%;
  background-color: #f2f3f5;
  width: 50px;
  height: 50px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.5s ease-in-out;
  color: black;
  overflow: hidden;
}

.nav-item:hover .nav-content {
  background-color: #0563bb;
  width: auto;
  border-radius: 28px;
  color: white;
}

.nav-item.active .nav-content {
  background-color: #0563bb;
  border-radius: 28px;
  color: white;
}

.nav-item:hover .nav-title {
  display: block;
  color: white;
}
</style>

