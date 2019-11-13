<template>
  <div>
    <!-- v-model 入力文字の引数 -->
    <input type="text" v-model="addText" />
    <!-- @click メソッド名 -->
    <button @click="addNew">追加</button>
  </div>
</template>

<script>
export default {
  name: "Add",
  data: function() {
    return {
      addText: ""
    };
  },
  methods: {
    /**
     * methods: addNew
     * 要素をAdd→Appへ
     */
    addNew: function() {
      this.$emit("passAdd", this.addText); // this.$emit('(関数名)', (引数))
      this.addText = ""; // ボタン押下後にフォームのリセット
    }
  }
};
</script>