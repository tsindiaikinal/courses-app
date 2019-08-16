<template>
  <div class="home">
    <h1>Welcome to our courses</h1>
    <img alt="Vue logo" src="../assets/book-open.svg" />
    <p @mouseover="hover">{{ result }}</p>
    <button @mouseover="hover" @click="count">counter++</button>
    <br />
    <button @click="result--">counter--</button>
    <table>
    <!-- <tr v-for="elem in users">
     <td >{{ elem.name }} </td>
     <td >{{ elem.email }} </td>
     <td >{{ elem.status }} </td>
   </tr> -->
    </table>
  </div>
</template>

<script>
export default {
  name: "home",
  components: {},
  data() {
    return {
      result: 0
    };
  },
  methods: {
    count: function() {
      return this.result += 2;
    },
    hover: function () {
      event.target.style.color = "red"
    }
  }
};
</script>

<style lang="scss" scoped>
h1 {
  margin-top: 4%;
}
#nav {
  border: 1px solid black;
}
img {
  width: 50%;
}
</style>
