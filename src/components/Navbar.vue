<template>
  <nav>
    <fa icon="bars" />
    <router-link :to="{ name: 'Home' }">
      <img src="../assets/coffeeStoreLogo.png" alt="" />
    </router-link>
    <fa icon="cart-shopping" />
  </nav>
</template>

<script>
export default {};
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
</style>
