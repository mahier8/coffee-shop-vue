<template>
  <div class="orderPageContainer">
    <h1>Order page</h1>
    <!-- if we have an error it will display, otherwise, 
    because error is set to null, nothing will display-->
    <div v-if="error">{{ error }}</div>
    <!-- to add a loading tag, we use posts.length, meaning if we have something in the array  -->
    <div v-if="orders.length">
      <OrderList :orders="orders" />
    </div>
    <!-- While we are waiting for the data, add in the loading -->
    <div v-else>Loading...</div>
  </div>
</template>

<script>
import OrderList from "../components/OrderList.vue";
import { ref } from "vue";

export default {
  name: "Order",
  components: { OrderList },
  setup() {
    const orders = ref([]);
    const error = ref(null); // 1. matches with

    const load = async () => {
      try {
        let data = await fetch("http://localhost:3000/orders");
        // console.log(data); we are just checking to see
        // if we get the data here

        if (!data.ok) {
          throw Error("no data available"); // 1. matches with
        }
        orders.value = await data.json();
      } catch (err) {
        error.value = err.message;
        console.log(error.value);
      }
    };

    load();

    return { orders, error };
  },
};
</script>

<style></style>
