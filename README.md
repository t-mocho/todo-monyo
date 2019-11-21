# todo-monyo memo

### 11/21 エラーがきえた
- 以下コードでエラーをはかなくなったけど、あしたみよう
    ```
        var i = 0;
        let plus = i.length;
        const add = {id: plus, value: addText}
    ```

### 11/19 idをプラスする←間違えてた
- `this.id++`用のmethod作ってもダメだったorz
- 18日分の解釈間違えていたyo
  - `:key="todo.idPlus"`この:keyに入るのはあくまで`id:`の部分で<br>
  現状だと`:key="todo.0"`（値のみ）になっているのでidを指定しなきゃいけない
  - `:key="todo.id"`は固定でidの中身が0,1,2,3になるよう進めていく

### 11/18 idをプラスする
- id:0 から1,2,3と++していく
  - `:key="todo.idPlus"`のkey変更
  - `var idPlus = this.id++`でidをidPlusにしたらいけた（for文いらないんだね）
- constに追加リスト作ってたけどvarでid++した変数をconstのs処理に突っ込んでもいけることを知った

### 11/17 リストに追加
- 値の話
  - let:同じメソッド内のみで
  - var:全部で変更できる値
  - const:固定値
- リストに追加した
  - emitで渡してv-onで受け取ってさらにv-bindでもらう
- 次の課題
  - 「id:4」固定になってるのをforするよ
  - searchで絞り込みするよ

### 11/16 macbookに設定追加してるよ
- macbookに環境構築中
- sorcetreeとgitとnode.jsと拡張機能とか諸々完了

### 11/13 component オオオ

- Add→App に emit する方法をりかい（alert で確認）
- push とか unshift の違いってなーにが以下サイトに載ってたよ<br>
  参考：https://maeharin.hatenablog.com/entry/20130122/unshift_shift_pop_push
- App.vue で`v-on: app-add="appAdd"`が反応なかったなんでだろう<br>
  なお`@app-add="appAdd"`で動いたもよう<br>
  **まさかの空白問題というオチだったよ！！** → 正しくは `v-on:app-add="appAdd"`

### 11/12 v-model とか components とか

- springboot と感覚似てる？ MVC （model）が出てきた ← 似てるけど違うらしい<br>
  参考：https://qiita.com/a-pompom/items/6c27d25bb44e0f754116
- どのサンプルも`export default`でスターとして name つけてた
- コンポーネント勉強しよう
  - 子 → 親は emit をつかう<br>
    参考：https://qiita.com/fukuman/items/b0bc84081ad0d2bc522a
  - 親 → 子は props をつかう<br>
    参考：https://qiita.com/fukuman/items/b7e15a8dab4ebb870952-
  - Todo 追加だけの意味だと Add→List→App の順番<br>
    App には全機能 import されてるけど List と Add はお互い import されていないから

### 11/11 v-for が使えたのとルールとか

- ベースが .html と .vue で javascript の書き方変わるよ
  - `new Vue` は .html に.vue を読み込んで処理するときに使われる（CDN とか vue ファイル・Babel 使ってるかも）
  - .vue で js 書くときは `export default`を使ったり data は関数型などルールがある
- README もテンプレートがあった

#### 11/11 v-for 解決編

- key ってなんだ
  - `v-for="todo in todolist" :key="todo"`<br>
    v-for を使う場合 :key が必要・一意に決まる値を指定する必要がある
- index ってなんだ
  - `"index in nakami"`<br>
    nakami を index に突っ込んで for するイメージ

### 11/10 v-for の謎

- v-for はじめました
- `v-for="index in nakami"` の index の意味に詰まる
- `Elements in iteration expect to have 'v-bind:key' directives.eslint-plugin-vue`<br>
  起動しようとしたら key 必要ってエラーが出てハマった

### 11/9 index.html に他の.vue を呼び出してみよう

- App.vue に Add~Search.vue を import すればよき
- index.html に import するのは App.vue のみで OK
