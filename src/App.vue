<template>
  <div id="app">
    <Nav />
    <Reputation :cards="reputation" />
    <CountText :count="count" />
    <Button text="Add one" @click="addCount" />
    <Button text="Minus one" @click="count--" />
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Reputation from "./components/Reputation.vue";
import Button from "./components/Button.vue";
import CountText from "./components/CountText.vue";

export default {
  name: "App",
  components: {
    Nav,
    Reputation,
    Button,
    CountText,
  },
  data() {
    return {
      name: "Serhii",
      count: 1,
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
  methods: {
    addCount(e) {
      console.log(e);
      this.count++;
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
