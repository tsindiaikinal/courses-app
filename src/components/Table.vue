<template>
  <div class="head">
    <nav>
      <div class="navbox">
        <dialog-window :popupData="popupData" @formDataTransfer="$event"></dialog-window>
        <search-panel></search-panel>
      </div>
      <h1>{{ title }}</h1>
      <select-display-pages></select-display-pages>
    </nav>
    <table>
      <thead>
        <tr class="table-header">
          <th>name</th>
          <th>e-mail</th>
          <th>status</th>
          <th>action</th>
        </tr>
      </thead>
      <tbody class="table-content">
        <tr class="table-content__elem">
          <td>{{ index }}</td>
          <td>{{ index }}</td>
          <td>{{ index }}</td>
          <td>{{ index }}</td>
        </tr>
      </tbody>
    </table>
    <pagination />
  </div>
</template>

<script>
import DialogWindow from "./DialogWindow";
import SearchPanel from "./SearchPanel";
import SelectDisplayPages from "./SelectDisplayPages";
import Pagination from "./Pagination";
export default {
  name: "TableTemplate",
  components: {
    DialogWindow,
    SearchPanel,
    SelectDisplayPages,
    Pagination
  },
  data: () => {
    return {
      title: "Courses",
      index: 0,
      headers: [],
      popupData: 'Testing transfer data',
      dataTable: [
        {
          users: {
            // name: editedItem.name,
            // email: editedItem.email,
            // status: editedItem.status
          }
        }
      ]
    };
  },
  props: {
    // dataTable: []
  }
};
</script>
<style lang="scss" scoped>
// COLORS
$white: #ffffff;
$darkgray: #565761;
// **********************

nav {
  margin: 5% auto;
  padding: 0 5px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

.navbox {
  width: 70px;
  display: flex;
  align-items: center;
}

h1 {
  width: 120px;
}

table {
  width: 100%;
  margin: 5% auto;
  .table-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1% 4% 1%;
    background-color: $darkgray;
    th {
      text-transform: uppercase;
      font-weight: lighter;
      color: $white;
    }
  }
  .table-content__elem {
    display: flex;
    justify-content: space-around;
    td {
      width: 100%;
      border: 1px solid grey;
    }
  }
}
</style>
