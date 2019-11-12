<template>
  <div id="app">
    App.vueだよ
    <Search />
    <List v-on: addTask="appList" />
    <ListDetail />
    <Add v-on: addTask="appAdd" />
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
  },

  methods: {
    /**
     * ListとAddを関連づけさせたい
     * @param addText フォームの入力値
     */
    appAdd: function(addText) {
      this.todoList.push()({
        id: 4,
        value: addText
      });
    }
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
