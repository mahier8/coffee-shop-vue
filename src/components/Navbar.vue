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
        <fa icon="bars" class="close-bar" @click="toggleMobileNav" />
        <router-link class="link" to="/order">Order/주문</router-link>
        <router-link class="link" to="#">Coupons/쿠폰</router-link>
        <router-link class="link" to="#">Events/이벤트</router-link>
        <router-link class="link" to="#">Stamps/우표</router-link>
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
  z-index: 2;
}

.mobile-nav-enter-active,
.mobile-nav-leave-active {
  transition: opacity 0.7s ease-in-out;
}

.mobile-nav-enter-from,
.mobile-nav-leave-to {
  opacity: 0;
}

.mobile-nav-enter-to,
.mobile-nav-leave-from {
  opacity: 1;
}

/* for the width transition, but had some problems with how the links loaded */
/* .mobile-nav-enter-active,
.mobile-nav-leave-active {
  transition: width 0.5s ease-in-out;
}

.mobile-nav-enter-from,
.mobile-nav-leave-to {
  width: 0;
}

.mobile-nav-enter-to,
.mobile-nav-leave-from {
  width: 250;
} */

.link {
  padding: 15px 0;
  color: #fff;
  text-decoration: none;
  border-bottom: 1px solid white;
}

.link:hover {
  background-color: #454444;
  margin-left: 0;
}

.close-bar {
  color: aliceblue;
  margin-bottom: 20px ;
  margin-right: 180px;
}
</style>
