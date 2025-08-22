<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <h3>Tembin</h3>
          <p>Creative Design Portfolio</p>
        </div>
        <div class="footer-links">
          <router-link to="/">Home</router-link>
          <a href="#about">About</a>
          <a href="#works">Works</a>
          <a href="#services">Services</a>
          <router-link to="/contact">Contact</router-link>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2024 Tembin. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>
