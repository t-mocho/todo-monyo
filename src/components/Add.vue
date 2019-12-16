<template>
  <div id="add">
    <!-- v-model 入力文字の引数 -->
    <input type="text" v-model="addText" />
    <!-- @click メソッド名 -->
    <b-button type="button" size="sm" class="btn btn-success" @click="addNew">追加</b-button>
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
<style>
#add {
  padding-bottom: 30px;
}
</style>