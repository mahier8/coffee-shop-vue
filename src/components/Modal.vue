<template>
  <!-- surrounding/behind the modal the dark/grey area -->
  <div class="backdrop" @click.self="closeModal">
    <!-- the modal itself -->
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      // a custom event, first argument is custom so it can be anything
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
/* the scoped property will causing to be local only, not global */

/* the modal */
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
/* the backdrop */
.backdrop {
  top: 0;
  /* added this in to remove white space on the left */
  left: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
h1 {
  border: none;
  padding: 0;
  color: aquamarine;
}

.modal.sale {
  background: crimson;
  color: white;
}

.modal.sale h1 {
  color: white;
}
</style>
