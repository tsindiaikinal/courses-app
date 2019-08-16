<template>
  <div class="select-pages">
    <label for="pages-count"></label>
    <select class="panel__pages-count" id="pages-count">
      <option value="5">5</option>
      <option value="10">10</option>
      <option value="15">15</option>
      <option value="all">All</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SelectDisplayPages",
  data: () => {
    return {};
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

label[for="pages-count"] {
  display: inline-block;
  &::after {
    content: "\f140";
    font-family: "Material Design Icons";
    vertical-align: middle;
    margin-right: -85px;
  }
}
.panel__pages-count {
  width: 60px;
  height: 30px;
  padding-left: 10px;
  outline: none;
  border: none;
  border-radius: 20px;
  background-color: $white;
  background: none;
  color: $lblack;
  cursor: pointer;
  @extend %shadow;
  -ms-progress-appearance: none;
  -moz-appearance: none;
  -webkit-appearance: none;
  appearance: none;
}
</style>