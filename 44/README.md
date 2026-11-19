# 44. 一覧を返すAPIの実装
/api/items というパスにGETリクエストが来た場合，idとnameを持つオブジェクトの配列をJSONで返すAPIを実装すること．

## ソースコード(.js)
```
const express = require("express");

const app = express();
const port = 3000;
```

`id`と`name`を持ったオブジェクトを要素とする配列`items`を事前に定義する。
```
const items = [
  { id: 1, name: "りんご" },
  { id: 2, name: "みかん" },
  { id: 3, name: "バナナ" }
];
```

動作確認用のルート（任意）
```
app.get("/", (req, res) => {
  res.send("Server is running");
});
```

`/api/items`に GET リクエストが来たときに JSON を返す
```
app.get("/api/items", (req, res) => {
  res.json(items);
});
```

サーバーを起動する
```
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
```

## curlコマンド
```
curl http://localhost:3000/api/items
```

## 出力結果
```
[{"id":1,"name":"りんご"},{"id":2,"name":"みかん"},{"id":3,"name":"バナナ"}]
```
