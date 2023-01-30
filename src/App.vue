<template>
  <div id="app">
    <Nav />
    <Reputation :cards="reputation" />
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Reputation from "./components/Reputation.vue";

export default {
  name: "App",
  components: {
    Nav,
    Reputation,
  },
  data() {
    return {
      reputation: [
        {
          header: "Best Services",
          text: "Nullam senectus porttitor in eget. Eget rutrum leo interdum.",
        },
        {
          header: "Reasons",
          text: "Cursus semper tellus volutpat aliquet lacus.",
        },
        {
          header: "Best Designs",
          text: "Ultricies at ipsum nunc, tristique nam lectus.",
        },
      ],
    };
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
</style>
