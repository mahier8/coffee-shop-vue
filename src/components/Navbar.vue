<template>
  <nav>
    <!-- to open the sidebar -->
    <fa icon="bars" @click="toggleMobileNav" />
    <!-- to toggle the mobile navigation/the menuIcon image import -->
    <!-- <menuIcon  class="menu-icon" v-show="mobile" /> -->
    <!-- for the mobile navigation -->
    <transition name="mobile-nav">
      <ul class="mobile-nav" v-show="mobileNav">
        <!-- to close the sidebar -->
        <fa icon="bars" @click="toggleMobileNav" />
        <router-link class="link" to="#">Home</router-link>
        <router-link class="link" to="#">Blogs</router-link>
        <router-link class="link" to="#">Create Post</router-link>
        <router-link class="link" to="#">Login/Register</router-link>
      </ul>
    </transition>
    <router-link :to="{ name: 'Home' }">
      <img src="../assets/coffeeStoreLogo.png" alt="" />
    </router-link>
    <fa icon="cart-shopping" />
  </nav>
</template>

<script>
// import the menu icon
export default {
  name: "navigation",
  components: {},
  // for the transitional menu sidebar depending on which viewport is being used
  data() {
    return {
      mobileNav: null,
    };
  },

  methods: {
    // a function to toggle the mobile nav
    // later, whatever we click will set  this.mobileNav
    // to the opposite of whatever it is at that moment
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },
  },
};
</script>

<style>
nav {
  background: aqua;
  height: 65px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
nav img {
  width: 11%;
}

.mobile-nav {
  padding: 20px;
  width: 70%;
  max-width: 250px;
  display: flex;
  flex-direction: column;
  position: fixed;
  height: 100%;
  background-color: #303030;
  top: 0;
  left: 0;
  /* for the sidebar to stand over the carousel */
  z-index: 999;
}
.link {
  padding: 15px 0;
  color: #fff;
}
</style>
