<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <CoursesComp msg="Welcome to Your Vue.js App"></CoursesComp>
  </div>
</template>

<script>
// @ is an alias to /src
import CoursesComp from "@/components/CoursesComp.vue";

export default {
  name: "Courses",
  components: {
    CoursesComp
  }
};
</script>

