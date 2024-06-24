<template>
  <Navbar />
  <main>
    <RouterView />
  </main>
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
  name: "App",
  components: {
    Navbar,
  },
  data() {
    return {
      title: "My First Vue app!",
      header: "Sign up for the giveaway!",
      text: "Grab your monkey moneys!",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
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
  list-style: none;
  color: #2c3e50;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
}
</style>
