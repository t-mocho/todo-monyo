# todo-monyo memo

### 11/11 v-model とか components とか

- springboot と感覚似てる？ MVC （model）が出てきた
  参考：https://qiita.com/a-pompom/items/6c27d25bb44e0f754116
- どのサンプルも``export default`でスターとして name つけてた
- コンポーネント勉強
  - 子 → 親は emit
    参考：https://qiita.com/fukuman/items/b0bc84081ad0d2bc522a
  - 親 → 子は props
    参考：https://qiita.com/fukuman/items/b7e15a8dab4ebb870952

### 11/11 v-for が使えたのとルールとか

- ベースが .html と .vue で javascript の書き方変わるよ
  - `new Vue` は .html に.vue を読み込んで処理するときに使われる（CDN とか vue ファイル・Babel 使ってるかも）
  - .vue で js 書くときは `export default`を使ったり data は関数型などルールがある
- README もテンプレートがあった

#### 11/11 v-for 解決編

- key ってなんだ
  - `v-for="todo in todolist" :key="todo"`
    v-for を使う場合 :key が必要・一意に決まる値を指定する必要がある
- index ってなんだ
  - `"index in nakami"`
    nakami を index に突っ込んで for するイメージ

### 11/10 v-for の謎

- v-for はじめました
- `v-for="index in nakami"` の index の意味に詰まる
- `Elements in iteration expect to have 'v-bind:key' directives.eslint-plugin-vue`
  起動しようとしたら key 必要ってエラーが出てハマった

### 11/9 index.html に他の.vue を呼び出してみよう

- App.vue に Add~Search.vue を import すればよき
- index.html に import するのは App.vue のみで OK
