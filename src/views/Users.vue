<template>
  <div class="users">
    <table-template></table-template>
  </div>
</template>

<script>
import TableTemplate from "@/components/Table.vue";

export default {
  name: "Users",
  components: {
    TableTemplate
  },
  data() {
    return {
      profile: "Users profile"
    };
  }
};
</script>

<style lang="scss" scoped>
.users {
  width: 80%;
  margin: auto;
}
</style>
