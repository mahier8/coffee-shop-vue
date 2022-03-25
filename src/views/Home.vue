<template>
  <Navbar />
  <div class="home">
    <Carousel class="carousel" v-slot="{ currentSlide }">
      <Slide v-for="(slide, index) in carouselSlides" :key="index">
        <div v-show="currentSlide === index + 1" class="slide-info">
          <img :src="require(`../assets/${slide}.jpg`)" alt="" />
        </div>
      </Slide>
    </Carousel>
  </div>
  <h1>{{ title }}</h1>
  <!-- the if condition, setting the modal to true -->
  <div v-if="showModal">
    <!-- our custom event is called close -->
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <!-- we click here to toggle the modal -->
  <button @click="toggleModal">Show Modal</button>
</template>

<script>
import Carousel from "../components/Carousel.vue";
import Slide from "../components/Slide.vue";

import Modal from "../components/Modal.vue";
import Navbar from "../components/Navbar.vue";
export default {
  name: "Home",
  components: {
    Modal,
    Navbar,
    Carousel,
    Slide,
  },
  data() {
    return {
      title: "Cafe Bom Bom",
      header: "Buy our coffee!",
      text: "Coffees are half price",
      showModal: false,
    };
  },
  setup() {
    const carouselSlides = ["cappucino", "coffeeAndCake", "muffin"];

    return {
      carouselSlides,
    };
  },
  // we need methods to introduce functions in the Options API
  methods: {
    toggleModal() {
      // we reverse the boolean here
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: #2c3e50;
}
h1 {
  color: blueviolet;
  display: inline-block;
  border-bottom: 1px solid blueviolet;
  padding-bottom: 10px;
}
button {
  color: white;
  background: blueviolet;
  border-style: none;
  border-radius: 8px;
  padding: 8px;
  margin-left: 10px;
}

/* the carousel */
.carousel {
  position: relative;
  max-height: 50vh;
  height: 50vh;
}
.slide-info {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  max-height: 100%;
  height: 100%;
}

.slide-info img {
  min-width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
