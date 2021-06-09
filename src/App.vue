<template>
  <div id="app">
    <div class="jumbotron">
      <h1>Trabajo Practico 6</h1>
      <br />
      <Navbar />
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";

export default {
  name: "App",
  components: {
    Navbar,
  },
};
</script>

<style>
#app {
}

h1 {
  color: green;
}

.jumbotron {
  padding: 32px !important;
}
</style>
