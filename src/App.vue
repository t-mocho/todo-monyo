<template>
  <div id="app">
    <p>searchtext:{{searchText}}</p>
    <Search v-on:passSearch="appSearch" v-on:passReset="appReset" />
    <List :todolist="todolist" :todolistSearch="todolistSearch" v-on:passCheck="appDel" />
    <Add v-on:passAdd="appAdd" />
  </div>
</template>

<script>
import Add from "./components/Add";
import List from "./components/List";
import Search from "./components/Search";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
import Vue from "vue";
import BootstrapVue from "bootstrap-vue";

Vue.use(BootstrapVue);

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
      // リスト一覧
      todolist: [
        { id: 0, value: "ごはん", del: false, end: false },
        { id: 1, value: "もぐもぐ", del: false, end: false },
        { id: 2, value: "はみがき", del: false, end: false }
      ],

      // nextId++
      nextId: 3,
      // searchTextに空文字
      searchText: ""
    };
  },

  computed: {
    todolistSearch: function() {
      // サーチの入力値がtodolistにあてはまるかみるよ
      if (this.searchText !== "") {
        return this.todolist.filter(todo => todo.value === this.searchText);
      }
      return this.todolist;
    }
  },

  methods: {
    // タスク追加処理
    appAdd: function(addText) {
      // v.lengthでidの数見て引数の入力値をpushする
      const add = { id: this.nextId++, value: addText, del: false, end: false };
      this.todolist.push(add);
    },

    // タスク削除処理
    appDel: function() {
      // falseのやつだけ
      var todoDel = this.todolist.filter(todo => todo.del === false);
      // todolistに上書き
      this.todolist = todoDel;
    },
    appSearch: function(text) {
      // passSearchから受け取った入力値をdata内のsearchTextにsetする
      this.searchText = text;
    },
    appReset: function(r) {
      this.searchText = r;
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
  margin-top: 0px;
  background-color: antiquewhite;
  border-radius: 0 0 15px 15px;
  border: solid #202020 2px;
  border-top: solid 0;
}
</style>
