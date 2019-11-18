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
  
  data() {
    return {
        todolist: [
          { id: 0, value: "その１"},
        ]
    }
  },
    
    methods: {
      appAdd: function(addText) {
        var idPlus = this.id++
        const add = {id: idPlus, value: addText}
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
