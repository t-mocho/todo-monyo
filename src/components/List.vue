<template>
  <div id="list">
    <!-- v-bind:props名="メソッド名" -->
    <li v-for="todo in todolist" :key="todo.id">
      <input type="checkbox" />
      <label>{{todo.value}}</label>
    </li>
  </div>
</template>

<script>
export default {
  name: "List",
props: ["todolist"]
};
</script>

<style>
#list {
  background-color: aquamarine;
}
</style>