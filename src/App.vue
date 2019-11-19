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
        todolist: [
          { id: 0, value: "その１"},
        ]
    }
  },
    
    // task追加処理
    methods: {

      idAdd: function(){
        this.id++
      },

      appAdd: function(addText) {
        const add = {id: this.idAdd, value: addText}
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
