<template>
  <div id="list">
    <!-- v-bind:props名="メソッド名" -->
    <li v-for="todo in todolist" :key="todo" v-bind:="addList">
      <input type="checkbox" />
      <label>{{todo.value}}</label>
    </li>
  </div>
</template>

<script>
export default {
  name: "List",
  props: ["passList"],

  data: function() {
    return {
      todolist: [
        { id: 1, value: "その１" },
        { id: 2, value: "その２" },
        { id: 3, value: "その３" }
      ]
    };
  },
  methods: {
    addList: function() {
      alert("hoge");
      this.todolist.push()({
        value: "passList"
      });
    }
  }
};
</script>

<style>
#list {
  background-color: aquamarine;
}
</style>