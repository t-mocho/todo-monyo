# todo-monyo memo

## 11/11 v-for 使ってみよう ☆ 解決編

- ベースが html と vue の違いで js の書き方が変わる
  new Vue は html に.vue を読み込んで処理するタイプで
  CDN か Vue のファイル `src=hoge.vue` とか使って HTML で読み込んでる（Babel？）
  .vue で js を記載するときは `export default` 等をつかいます
- v-for を使う場合は :key が必要で一意に決まる値を指定する必要がある
- index に nakami を突っ込んで回すイメージで nakami は js で作る
  vue に記載する js の書き方は data は関数じゃなきゃだめよ～とかルールがあるので
  html に.vue を読み込ませて書くコードとはまた違ってくる

`v-for="index in nakami" :key="index"`

```
export default {
  name: "nakamiList",
  data: function() {
    return {
      nakami: [
        { title: "イチ", id: 1 },
        { title: "ニ", id: 2 },
        { title: "サン", id: 3 }
      ]
    };
  }
};
```

## 11/10 v-for 使ってみよう

- v-for はじめました
- index.item の index の意味に詰まる
- key 必要ってエラーが出てハマった

`v-for="index in nakami"`
`Elements in iteration expect to have 'v-bind:key' directives.eslint-plugin-vue`

## 11/9 index.html に他の.vue を呼び出してみよう

- App.vue に Add~Search.vue を import すればよき
- index.html に import するのは App.vue だけで OK

```
export default {
  el: "#app",
  components: {
    Add,
    List,
    Search,
    ListDetail
  }
};
```
