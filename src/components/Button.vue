<template>
  <button @click="sendInfo">{{ text }}</button>
</template>

<script>
export default {
  name: "Button",
  props: ["text"],
  methods: {
    sendInfo() {
      const info = {
        text: this.text,
        isClicked: true,
      };
      this.$emit("click", info);
    },
  },
};
</script>

<style>
</style>