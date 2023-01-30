<template>
  <a class="nav__link" :href="href">{{ title }}</a>
</template>

<script>
export default {
  name: "Link",

  props: ["href", "title"],
};
</script>

<style>
.nav__link {
  text-decoration: none;
  font-weight: 400;
  font-size: 18px;
  line-height: 21px;
  color: #14171f;
}

.nav__link:focus,
.nav__link:hover {
  font-weight: 600;
  font-size: 18px;
  line-height: 21px;
  color: #f9995d;
}
</style>