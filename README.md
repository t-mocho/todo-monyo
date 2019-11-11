# todo-monyo memo

###### 11/11 v-for はあく。ベースが html と vue の違いで js の書き方が変わることを知ったよ

`v-for="index in nakami" :key="index"`

- :key が必要だったよ（一意に決まる値を指定）
- index に nakami を突っ込んで回すよ
- nakami は js で作るよ

```
export default {
  name: "nakamiList", <>
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

- new Vue は html に.vue を読み込んで処理するタイプだよ（CDN か Vue のファイル HTML で読み込んでる/Babel？）
  →vue に記載する data は関数じゃなきゃだめよ～とかルールがあったよ

###### 11/10 v-for に苦戦

`v-for="index in nakami"`

- index.item の index の意味に詰まる
  `Elements in iteration expect to have 'v-bind:key' directives.eslint-plugin-vue`
- key 必要ってエラーが出てハマった

###### 11/9 Git 作ったよ。App.vue で他の vue 制御するよ

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

- App.vue に Add~Search.vue を import して制御するよ

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
