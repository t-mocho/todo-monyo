<template>
  <div id="app">
    <Search />
    <List
    :todolist="todolist"
    v-on:passCheck="appDel" />
    <Add v-on:passAdd="appAdd" />
  </div>
</template>

<script>
import Add from "./components/Add";
import List from "./components/List";
import Search from "./components/Search";

// コンポーネント
export default {
  name: "importAll",
  components: {
    Add,
    List,
    Search
  },
  
  // todoリスト
  data() {
    return {
        todolist: [
          {id: 0, value: "たぴ０", del: false},
          {id: 1, value: "たぴ１", del: true},
          {id: 2, value: "たぴ２", del: false},
          ]
    }
  },
    
    methods: {
      // タスク追加処理
      appAdd: function(addText) {
        // keysで配列オブジェクトがなんこあるかわかるよ
        var v = Object.keys( this.todolist );
        // v.lengthでidの数見て引数の入力値をpushする
        const add = {id: v.length, value: addText, del: false}
        this.todolist.push(add);
        },
      
      // タスク削除処理
      appDel: function() {
        // falseのやつだけ
        var todoDel = this.todolist.filter(todo => todo.del === false);
        // todolistに入れる
        this.todolist = todoDel
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
