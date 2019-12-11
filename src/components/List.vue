<template>
  <div id="list">
    <table>
      <tbody>
        <!-- transition-groupで複数リストにアニメーションをつける -->
        <transition-group name="anime" tag="th">
          <!-- todolistをforして表示 -->
          <tr v-for="todo in todolistSearch" :key="todo.id" class="animelist">
            <th>
              <!-- 削除用checkbox -->
              <input type="checkbox" name="check1" v-model="todo.del" />
            </th>
            <!-- 完了押下でiconimg切替 -->
            <span class="in" v-if="todo.end===true">
              <img class="icon" src="../assets/img/ok.png" />
            </span>
            <img class="icon" v-else src="../assets/img/mada.png" />
            <!-- showでアニメーション付与 -->
            <th class="task" v-if="show">
              <!-- :classで完了押下で取消線 -->
              <span :class="{ todoEnd: todo.end }">{{ todo.value }}</span>
            </th>
            <th>
              <!-- b-button bootstrap-->
              <b-button variant="info" size="sm" @click="todo.end=true">完了</b-button>
            </th>
          </tr>
        </transition-group>
      </tbody>
    </table>
    <b-button variant="warning" size="sm" @click="todoDel">削除</b-button>
  </div>
</template>

<script>
export default {
  name: "List",
  // Appからtodolist,todolistsearchを受け取る
  props: ["todolist", "todolistSearch"],

  data: function() {
    return {
      show: true
    };
  },
  methods: {
    todoDel: function() {
      // todoDelをAppに渡す
      this.$emit("passCheck"); // this.$emit('(関数名)'
    }
  }
};
</script>

<style>
/** img icon */
.icon {
  border-radius: 50%;
  width: 80px;
  height: 80px;
}
.animelist {
  transition: all 1s;
}
/** todo fade in */
.anime-enter {
  opacity: 0;
  transform: translateX(20px);
}
/** todo fade out */
.anime-leave-to {
  opacity: 0;
  transform: translateX(20px);
}
/** img切替 */
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
/** 行間調整 */
#list {
  line-height: 3;
}
/** table */
table {
  border-collapse: collapse;
  border-spacing: 0;
  margin: auto;
  width: 50%;
}
/** table tr */
table tr {
  border-bottom: solid 1px #c4c4c4;
}
/** hover時 */
table tr:hover {
  background-color: #d4f0fd;
}
/** th,td文字中央 */
table th,
table td {
  text-align: center;
}
/** 吹き出し風に */
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
/** 完了ボタンで取消線 */
.todoEnd {
  text-decoration: line-through;
  opacity: 80%;
}
</style>