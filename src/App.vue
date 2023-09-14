<template>
  <h1>{{ title }}</h1>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Hello</a>
        <a href="#">World</a>
      </template>
      <h1>Hello World</h1>
      <p>This is the hello world text</p>
    </Modal>
  </teleport>
  <button @click.alt="toggleModal">Show Modal (alt)</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First Vue App :-)",
      header: "My Modal",
      text: "this is modal body",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
  }
};
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
