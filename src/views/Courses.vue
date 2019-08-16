<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <courses-component msg="Welcome to Your Vue.js App"></courses-component>
  </div>
</template>

<script>
// @ is an alias to /src
import CoursesComponent from "@/components/CoursesComp.vue";

export default {
  name: "Courses",
  components: {
    CoursesComponent
  }
};
</script>
