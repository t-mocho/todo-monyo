<template>
  <div id="app">
    <Search />
    <List :todolist="todolist" />
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
  
  // todoリスト
  data() {
    return {
        todolist: []
    }
  },
    
    // task追加処理
    methods: {
      appAdd: function(addText) {
        var i = 0;
        let plus = i.length;
        const add = {id: plus, value: addText}
        this.todolist.push(add);
      }
    }
}
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
