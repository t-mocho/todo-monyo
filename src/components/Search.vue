<template>
  <div>
    <!-- v-model 入力文字の引数 -->
    <input type="text" v-model="searchText" @input="searchNew"/>
    <!-- @click メソッド名 -->
    <button @click="newBtn" value="検索">検索</button>
    <button @click="resetBtn">リセット</button>
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
    // text.target.valueで変更されるとリアルタイムに渡してくれる
    searchNew: function(changeText) {
      this.$emit("passSearch", changeText.target.value);
    },
    // text.target.valueで変更されるとリアルタイムに渡してくれる
    newBtn: function() {
      this.$emit("passSearch", this.searchText);
    },
    // 検索値を空にするよ
    resetBtn: function(){
      this.searchText = ""
      this.$emit("passReset", this.searchText);
    }
  }
};
</script>