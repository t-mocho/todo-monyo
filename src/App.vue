<template>
  <div id="app">
    App.vueだよ
    <Search />
    <List />
    <ListDetail />
    <Add />
  </div>
</template>

<script>
import Add from "./components/Add";
import List from "./components/List";
import Search from "./components/Search";
import ListDetail from "./components/ListDetail";

// 読み込み
export default {
  name: "importAll",
  components: {
    Add,
    List,
    Search,
    ListDetail
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
