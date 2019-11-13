<template>
  <div id="app">
    <Search />
    <List v-bind:passList="appAdd" />
    <ListDetail />
    <Add v-on:passAdd="appAdd" />
  </div>
</template>

<script>
import Add from "./components/Add";
import List from "./components/List";
import Search from "./components/Search";
import ListDetail from "./components/ListDetail";

// コンポーネント
export default {
  name: "importAll",
  components: {
    Add,
    List,
    Search,
    ListDetail
  },
  data() {
    return {
      appAdd: function(addText) {
        Set.value = addText;
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
  color: chocolate;
  margin-top: 60px;
  background-color: antiquewhite;
}
</style>
