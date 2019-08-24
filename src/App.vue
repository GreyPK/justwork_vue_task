<template>
  <div id="app">
    <vuetable
      class="vuetable"
      api-url="https://vuetable.ratiw.net/api/users"
      :fields="tableFields"
      :css="css"
      row-class="vuetable__row"
      data-path="data"
      table-height="30vh"
      ref="table"
      pagination-path
    ></vuetable>
  </div>
</template>

<script>
import vuetable from "vuetable-2";

export default {
  name: "App",
  components: {
    vuetable
  },
  data() {
    return {
      tableFields: [
        {
          name: "id",
          title: "№",
          width: "50px",
          sortField: "id",
          titleClass: "align-left",
          dataClass: "align-left"
        },
        {
          name: "name",
          title: "Наименование",
          width: "190px",
          sortField: "name",
          titleClass: "align-left",
          dataClass: "align-left"
        },
        {
          name: "email",
          title: "Почта",
          width: "250px",
          titleClass: "align-left",
          dataClass: "align-left"
        },
        {
          name: "birthdate",
          title: "Дата",
          width: "200px",
          titleClass: "align-left",
          dataClass: "align-left"
        }
      ],
      css: {
        ascendingIcon: "sort-up",
        descendingIcon: "sort-down"
      }
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.align-left {
  text-align: left;
}

.vuetable {
  border-spacing: 0;
}

.vuetable td {
  padding: 15px 0;
  border-bottom: 1px solid transparent;
  border-top: 1px solid transparent;
}

.vuetable th {
  border-bottom: 2px solid #ddd;
  text-transform: uppercase;
  padding: 15px 0;
}

.vuetable td:first-child,
.vuetable th:first-child {
  padding-left: 15px;
  border-left: 1px solid transparent;
}

.vuetable td:last-child {
  border-right: 1px solid transparent;
}

.vuetable__row:hover td {
  border-bottom: 1px solid #2185d0;
  border-top: 1px solid #2185d0;
}

.vuetable__row:hover td:first-child {
  border-left: 1px solid #2185d0;
}

.vuetable__row:hover td:last-child {
  border-right: 1px solid #2185d0;
}

.sort-up {
  content: url(assets/up.svg);
  vertical-align: middle;
  float: none !important;
}

.sort-down {
  content: url(assets/down.svg);
  vertical-align: middle;
  float: none !important;
}
</style>
