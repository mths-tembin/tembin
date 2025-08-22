<template>
  <nav class="navbar" :class="{ 'scrolled': isScrolled }">
    <div class="nav-container">
      <div class="nav-logo">
        <router-link to="/">Tembin</router-link>
      </div>
      <ul class="nav-menu" :class="{ 'active': isMenuOpen }">
        <li><router-link to="/" class="nav-link" @click="closeMenu">Home</router-link></li>
        <li><a href="#about" class="nav-link" @click="closeMenu">About</a></li>
        <li><a href="#works" class="nav-link" @click="closeMenu">Works</a></li>
        <li><a href="#services" class="nav-link" @click="closeMenu">Services</a></li>
        <li><router-link to="/contact" class="nav-link" @click="closeMenu">Contact</router-link></li>
      </ul>
      <div class="hamburger" @click="toggleMenu" :class="{ 'active': isMenuOpen }">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isScrolled: false,
      isMenuOpen: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 100
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    closeMenu() {
      this.isMenuOpen = false
    }
  }
}
</script>

<style scoped>
.navbar.scrolled {
  background: rgba(8, 33, 28, 0.98) !important;
}

.hamburger.active span:nth-child(1) {
  transform: rotate(-45deg) translate(-5px, 6px);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
}

.hamburger.active span:nth-child(3) {
  transform: rotate(45deg) translate(-5px, -6px);
}
</style>
