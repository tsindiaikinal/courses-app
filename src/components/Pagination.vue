<template>
  <div class="text-center">
    <v-pagination
      id="pagination"
      v-model="page"
      :length="6"
      prev-icon="mdi-chevron-left"
      next-icon="mdi-chevron-right"
    ></v-pagination>
  </div>
  <!-- <div class="pagination">
    <ul id="pages-container">
      <li>
        <button>
          <i class="mdi mdi-chevron-left"></i>
        </button>
      </li>
      <li>
        <button>1</button>
      </li>
      <li>
        <button>
          <i class="mdi mdi-chevron-right"></i>
        </button>
      </li>
    </ul>
  </div>-->
</template>

<script>
export default {
  data() {
    return {
      page: 1
    };
  }
};
</script>

<style lang="scss" scoped>
// COLORS
$lblack: #35495e;
$white: #ffffff;
$lgreen: #59b983;

button.v-pagination__item--active {
  background-color: $lgreen;
  color: red;
}

#pages-container {
  display: flex;
  justify-content: center;
  list-style-type: none;
  li {
    padding-left: 10px;
    padding-right: 10px;
    button {
      width: 30px;
      height: 30px;
      border: 0 solid #35495e;
      border-radius: 4px;
      background-color: $white;
      box-shadow: 0 1px 4px rgba($color: #000000, $alpha: 0.6);
      i {
        text-align: center;
        line-height: 30px;
      }
    }
  }
}
</style>
