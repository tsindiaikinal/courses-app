<template>
  <div id="search-panel">
    <form>
      <label for="search-field"></label>
      <!-- eslint-disable-next-line -->
      <input
        class="panel__search"
        type="search"
        name
        id="search-field"
        placeholder="search ..."
        v-model="search"
      />
    </form>
  </div>
</template>

<script>
export default {
  name: "SearchPanel",
  data: () => {
    return {
      search: []
    };
  }
};
</script>

<style lang="scss" scoped>
// COLORS
$lgrey: lightgrey;
$lblack: #35495e;
$white: #ffffff;
$lgreen: #59b983;
$red: #f60000;
// **************

%shadow {
  box-shadow: 0 1px 4px rgba($color: #000000, $alpha: 0.6);
}

form {
  margin-left: 20px;
  label[for="search-field"] {
    display: inline-block;
    position: relative;
    top: -20px;
    &::before {
      content: "\f349";
      font-family: "Material Design Icons";
      padding: 7px;
      position: absolute;
      margin-left: -2px;
      border-radius: 50%;
      vertical-align: middle;
      background-color: $lgreen;
      color: $white;
      text-shadow: 0 2px 3px $lblack;
    }
  }
  .panel__search {
    width: 180px;
    height: 30px;
    padding-left: 40px;
    padding-right: 10px;
    outline: none;
    border: 1px solid $lgrey;
    border-left: none;
    border-radius: 20px;
    @extend %shadow;
  }
  .panel__search:focus {
    border-color: $lgreen;
    border-left: none;
  }
}
</style>