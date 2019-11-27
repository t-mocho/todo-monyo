<template>
  <div id="list">
    <!-- 一覧 -->
    <li v-for="todo in todolistSearch" :key="todo.id">
      <input type="checkbox" v-model="todo.del"/>
      <label>{{todo.del}} : {{todo.id}} : {{todo.value}}</label>
    </li>
    <button @click="todoDel">削除</button>
  </div>
</template>

<script>
export default {
  name: "List",
  // appから受け取り
props: ["todolist", "todolistSearch"],

methods: {
  todoDel: function(){
    // 削除パス
    this.$emit("passCheck"); // this.$emit('(関数名)'
    }
  }
}

</script>

<style>
#list {
  background-color: aquamarine;
}
</style>