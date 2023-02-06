<template>
  <nav class="nav">
    <Link
      v-for="link in links"
      :key="link.href"
      :href="link.href"
      :title="link.title"
    />
  </nav>
</template>

<script>
import Link from "./Link.vue";

export default {
  name: "Nav",
  components: {
    Link,
  },
  data() {
    return {
      links: [
        {
          href: "main",
          title: "Home",
        },
        {
          href: "about-us",
          title: "About us",
        },
        {
          href: "services",
          title: "Services",
        },
        {
          href: "footer",
          title: "Contact us",
        },
      ],
    };
  },
};
</script>

<style scoped>
.nav {
  display: flex;
  justify-content: center;
  gap: 15px;
}
</style>