<template>
  <div class="app" id="app">
    <Nav />
    <Reputation :cards="reputation" />
    <div>{{ text }}</div>
    <CountText :count="count" />
    <Button text="Add one" @click="addCount" />
    <Button text="Minus one" @click="count--" />
    <Input @input="addText" />
    <Todolist class="app__todolist" />
  </div>
</template>

<script>
import Nav from "./components/firstLessons/Nav.vue";
import Reputation from "./components/firstLessons/Reputation.vue";
import Button from "./components/firstLessons/Button.vue";
import CountText from "./components/firstLessons/CountText.vue";
import Input from "./components/firstLessons/Input.vue";
import Todolist from "./components/todoList/Todolist.vue";

export default {
  name: "App",
  components: {
    Nav,
    Reputation,
    Button,
    CountText,
    Input,
    Todolist,
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

<style lang="scss" scoped>
#app {
  box-sizing: border-box;
  margin: 0px auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: aqua;
  padding: 20px;

  &__todolist {
    margin-bottom: 20px;
  }
}
</style>
