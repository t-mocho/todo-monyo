<template>
  <div id="list">
    <!-- v-bind:props名="メソッド名" -->
    <li v-for="(todo, index) in todolist" :key="todo.id">
      <input type="checkbox" />
      <label>{{index++}} : {{todo.value}}</label>
    </li>
  </div>
</template>

<script>
export default {
  name: "List",
  // appから受け取り
props: ["todolist"],
}

</script>

<style>
#list {
  background-color: aquamarine;
}
</style>