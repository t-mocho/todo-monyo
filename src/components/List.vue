<template>
  <div id="list">
    <table>
      <tbody>
        <transition-group name="”fade”">
          <tr class="in" v-for="todo in todolistSearch" :key="todo.id">
            <!-- 削除用checkbox -->
            <th>
              <input type="checkbox" name="check1" v-model="todo.del" />
            </th>
            <!-- 完了icon切替 -->
            <span class="in" v-if="todo.end===true">
              <img src="../assets/img/icon2.png" width="80px" height="80px" />
            </span>
            <img v-else src="../assets/img/icon1.png" width="80px" height="80px" />
            <!-- tasklist -->
            <th class="task">
              <span :class="{ todoEnd: todo.end }">{{ todo.value }}</span>
            </th>
            <th>
              <b-button variant="info" size="sm" @click="todo.end=true">完了</b-button>
            </th>
          </tr>
        </transition-group>
      </tbody>
    </table>
    <!-- ここのv-bind:classが間違っている気がした -->
    <b-button variant="warning" size="sm" @click="todoDel" v-bind:class="{out:todoDel}">削除</b-button>
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
@keyframes fadeOut {
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
.out {
  animation: fadeOut 2s;
}
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
.in {
  animation: fadeIn 0.5s;
}
#list {
  line-height: 4;
}
thead {
  background: rgb(255, 178, 249);
}
table {
  border-collapse: collapse;
  border-spacing: 0;
  margin: auto;
  width: 50%;
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
.task {
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

.task:before {
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

.demo1 .label_list:nth-of-type(1) label input[type="checkbox"] + span::before {
  border-color: #00acc1;
}
</style>