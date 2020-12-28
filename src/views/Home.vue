<template>
  <section class="hero is-primary is-fullheight">
  
    <HeroNavbar :routes="HeroNavbarRoutes" />

    <div class="hero-head"></div>

    <div class="hero-body">
      <div class="container has-text-centered">
        <h2 class="subtitle"><font-awesome-icon icon="home" /></h2>
        <h1 class="title">Home</h1>
      </div>
    </div>
  </section>
</template>

<script>
import HeroNavbar from "../components/HeroNavbar.vue";

export default {
  components: {
    HeroNavbar,
  },
  data() {
    return {
      HeroNavbarRoutes: [
        { "menu-name": "Home", "route-url": "/" },
        { "menu-name": "Contact", "route-url": "/contact" },
      ],
    };
  },
};
</script>