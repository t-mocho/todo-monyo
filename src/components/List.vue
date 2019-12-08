<template>
  <div>
    <table id="center">
      <!-- テーブルヘッダー -->
      <thead>
        <tr>
          <th>delete</th>
          <th>task</th>
          <th>end</th>
        </tr>
      </thead>
      <tbody id="table">
        <tr v-for="todo in todolistSearch" :key="todo.id">
          <!-- 削除用checkbox -->
          <th>
            <input type="checkbox" v-model="todo.del" />
          </th>
          <!-- 完了icon切替 -->
          <span id="icon" v-if="todo.end===true">
            <img src="../assets/img/icon2.png" width="80px" height="80px" />
          </span>
          <img id="icon" v-else src="../assets/img/icon1.png" width="80px" height="80px" />
          <!-- tasklist -->
          <th class="balloon3-left">
            <span :class="{ todoEnd: todo.end }">{{ todo.value }}</span>
          </th>
          <th>
            <b-button variant="info" size="sm" @click="todo.end=true">完了</b-button>
          </th>
        </tr>
      </tbody>
    </table>
    <b-button variant="warning" size="sm" @click="todoDel">削除</b-button>
  </div>
</template>

<script>
export default {
  name: "List",
  // appから受け取り
  props: ["todolist", "todolistSearch"],

  methods: {
    todoDel: function() {
      // 削除パス
      this.$emit("passCheck"); // this.$emit('(関数名)'
    }
  }
};
</script>

<style>
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  30% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
#icon {
  animation: fadeIn 0.5s;
}
thead {
  background: rgb(255, 178, 249);
}
table {
  border-collapse: collapse;
  border-spacing: 0;
  margin: auto;
}
table tr {
  border-bottom: solid 1px #c4c4c4;
}
table tr:hover {
  background-color: #d4f0fd;
}
table th,
table td {
  text-align: center;
}
.balloon3-left {
  position: relative;
  display: inline-block;
  margin: 1.5em 0 1.5em 15px;
  padding: 0 5px;
  width: 180px;
  height: 50px;
  line-height: 50px;
  text-align: center;
  color: #fff;
  font-size: 15px;
  font-weight: bold;
  background: #ffcc75;
  border-radius: 10px; /* 角丸指定*/
  box-sizing: border-box;
}

.balloon3-left:before {
  content: "";
  position: absolute;
  top: 50%;
  left: -25px;
  margin-top: -20px;
  border: 15px solid transparent;
  border-right: 50px solid #ffcc75;
  z-index: 0;
}

.todoEnd {
  text-decoration: line-through;
  opacity: 80%;
}
</style>