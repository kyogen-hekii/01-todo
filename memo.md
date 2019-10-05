[todo]("https://qiita.com/moonglows76/items/358ef3cd1566c38ece3a")
### Home.vue
WorldをTodoViewに変更
### TodoView.vue
1. 最初の表示
template 何を表示しようか
li todo in todos
vdata 何を使うか
todos: []
2. checkboxを追加したい
input→vmodel→data
3. テキストボックスの追加
enterでリストに追加
4. checkすると取消線
5. delボタンでチェックしたやつ削除

4. jankenを修正
* template
* 敵の手, 自分の手, 結果
```html
<!-- 結果 -->
{{ result }}
<!-- 敵の手 -->
{{ enemyHand }}
<!--自分の手(選択)-->
<button>グー</button>
<button>チョキ</button>
<button>パー</button>
```
* つかう変数を定義
vdata
```js
data() {
return {
result: '',
enemyHand: '',
};
},
```
* イベントハンドラーの定義
```html
<button @click="fight('goo')">グー</button>
```
vmethods
```js
fight(myHand){
this.enemyHand = Math.floor(Math.random() * 3);
// ...
}
```
option + command + iで開発ツールを表示
consoleに切り替えて確認
