<template>
  <div id="list">
    <li v-for="todo in todolist" :key="todo">
      <label>
        <input type="checkbox" v-model="todoList" />
        {{todo.value}}
      </label>
    </li>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      todolist: [
        { id: 1, value: "その１" },
        { id: 1, value: "その２" },
        { id: 1, value: "その３" }
      ]
    };
  }
};
</script>

<style>
#list {
  background-color: aquamarine;
}
</style>