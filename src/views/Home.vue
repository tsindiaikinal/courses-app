<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
  </div>
</template>

<script>
// @ is an alias to /src
import header from "@/components/header.vue";

export default {
  name: "home",
  components: {
    header
  }
};
</script>
<style lang="scss">
  #nav {
    border: 1px solid black;
  }
</style>
