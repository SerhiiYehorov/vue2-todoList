<template>
  <input v-model="text" />
</template>

<script>
export default {
  name: "Input",

  data() {
    return {
      text: "",
    };
  },

  watch: {
    text() {
      this.$emit("input", this.text);
    },
  },
};
</script>

<style scoped>
input {
  display: block;
  margin: 25px auto;
}
</style>