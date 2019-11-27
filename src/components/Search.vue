<template>
  <div>
    <!-- v-model 入力文字の引数 -->
    <input type="text" v-model="searchText" />
    <!-- @click メソッド名 -->
    <button @click="searchNew">検索</button>
  </div>
</template>

<script>
export default {
  name: "Search",
  data: function() {
    return {
      searchText: ""
    };
  },
  methods: {
    /**
     * methods: addNew
     * 要素をAdd→Appへ
     */
    searchNew: function() {
      this.$emit("passSearch", this.searchText, this.searchText + '2'); // this.$emit('(関数名)', (引数))
    }
  }
};
</script>