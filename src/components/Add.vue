<template>
  <div>
    <!-- テスト -->
    <input type="text" v-model="addText" />
    <button @click="addTask">追加</button>
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
     * 要素を子→親へ
     */
    addNew: function() {
      this.$emit("addTask", this.addText); // this.$emit('(関数名)', (引数))
      this.addText = "";
    }
  }
};
</script>