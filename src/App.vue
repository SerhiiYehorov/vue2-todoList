<template>
  <div id="app">
    <Nav />
    <Reputation :cards="reputation" />
    <div>{{ text }}</div>
    <CountText :count="count" />
    <Button text="Add one" @click="addCount" />
    <Button text="Minus one" @click="count--" />
    <Input @input="addText" />
  </div>
</template>

<script>
import Nav from "./components/Nav.vue";
import Reputation from "./components/Reputation.vue";
import Button from "./components/Button.vue";
import CountText from "./components/CountText.vue";
import Input from "./components/Input.vue";

export default {
  name: "App",
  components: {
    Nav,
    Reputation,
    Button,
    CountText,
    Input,
  },
  data() {
    return {
      name: "Serhii",
      surname: "Yehorov",
      count: 1,
      text: "",
      reputationItems: [
        {
          header: "Best Services",
          text: "Nullam senectus porttitor in eget. Eget rutrum leo interdum.",
        },
        {
          header: "",
          text: "Cursus semper tellus volutpat aliquet lacus.",
        },
        {
          header: "Best Designs",
          text: "Ultricies at ipsum nunc, tristique nam lectus.",
        },
      ],
    };
  },
  computed: {
    reputation() {
      return this.reputationItems.filter((item) => !!item.header);
    },
    fullName() {
      return `${this.name} ${this.surname}`;
    },
  },
  watch: {
    count() {
      this.name += "a";
    },
  },
  methods: {
    addCount() {
      this.count++;
    },
    addText(text) {
      this.text = text;
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
