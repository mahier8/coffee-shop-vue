<template>
  <div class="post">
    <img src="{{order.image}}" alt="" />
    <h3>
      {{ order.title }} <span>{{ order.price }}</span>
    </h3>
  </div>
</template>

<script>
export default {
  // our prop from the PostList component
  props: ["order"],
  setup() {},
};
</script>

<style></style>
