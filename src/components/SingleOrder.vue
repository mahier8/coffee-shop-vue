<template>
  <div class="singleOrderCard">
    <img :src="require('../assets/' + order.image)" alt="{{order.title}}" class="singleOrderCardImage" />
    <!-- <img :src="require('./assets/logo.png')"/>
    v-bind:style="{ 'background-image': 'url(' + require('../assets/img/covers/' + story.cover) + ')' }" -->
<!-- 
    </div> -->
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

<style>
.singleOrderCard {
  width: 200px;
  height: 200px;
  border-radius: 8px;
  padding: 10px;
  margin: 20px;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  cursor: pointer;
}
.singleOrderCardImage {
    width: 30%;

}
</style>
