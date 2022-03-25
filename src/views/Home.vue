<template>
  <Navbar />
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
import Modal from "../components/Modal.vue";
import Navbar from "../components/Navbar.vue";
export default {
  name: "Home",
  components: {
    Modal,
    Navbar,
  },
  data() {
    return {
      title: "Cafe Bom Bom",
      header: "Buy our coffee!",
      text: "Coffees are half price",
      showModal: false,
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
</style>
