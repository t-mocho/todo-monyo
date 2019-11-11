<template>
  <div id="list">
    <li v-for="todo in todolist" :key="todo">
      <label>
        <input type="checkbox" v-model="todo.isChecked" />
        {{ todo.title }}
      </label>
    </li>
  </div>
</template>

<script>
export default {
  name: "todoTable",
  data: function() {
    return {
      todolist: [
        { title: "イチ", id: 1 },
        { title: "ニ", id: 2 },
        { title: "サン", id: 3 }
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