<template>
  <div class="post-list">
    <!-- creating a for loop -->
    <div v-for="order in orders" :key="order.id">
      <SingleOrder :order="order" />
    </div>
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from "@vue/runtime-core";
import SingleOrder from "./SingleOrder.vue";
export default {
  components: { SingleOrder },
  props: ["orders"],
  setup() {
    onMounted(() => console.log("component mounted"));
    onUnmounted(() => console.log("component unmounted"));
    onUpdated(() => console.log("component updated"));
  },
};
</script>

<style></style>
