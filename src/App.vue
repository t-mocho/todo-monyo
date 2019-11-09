<template>
  <div id="app">
    App.vueだよ
    <App>
      <Add />
      <Delete />
      <Search />
      <Update />
    </App>
  </div>
</template>

<script>
import Add from "./components/Add";
import Delete from "./components/Delete";
import Search from "./components/Search";
import Update from "./components/Update";
export default {
  // 読み込むの
  components: {
    Add,
    Delete,
    Search,
    Update
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
