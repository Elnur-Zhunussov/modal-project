<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div to="modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal" :childText="suck">
      <h1>"Sign up for the Giveaway"</h1>
      <p>"Don't miss your chance!"</p>
    </Modal>
  </div>
  <button @click="toggleModal">Welcome</button>

  <p>Unwelcome ...</p>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo" :childText1="suck">
      <h1>"Go away please!"</h1>
      <p>"LOL"</p>
    </Modal>
  </div>
  <button @click="toggleModalTwo">Unwelcome</button>
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
      title: "My First Vue App",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
