# 41. シンプルなHTTPサーバ
Node.jsとExpressを使い，「Hello, API!」と返すだけのHTTPサーバを実装すること．

## ソースコード(.js)

エクスプレスを用意
```
const express = require("express");
const app = express();
```

データを届けるために識別するポート番号を設定
```
const port = 3000;
```

トップページ（`/`）に GETリクエスト（ブラウザや curl でアクセスしたときの基本的なリクエスト）が届いたときの処理を登録
+ `(req, res) => { ... }`  アクセスがあったときに呼ばれる関数(req がリクエスト情報、res がレスポンス)
+ `res.send("Hello, API!");`  アクセス元に対して "Hello, API!" という文字列を返す。
```
app.get("/", (req, res) => {
  res.send("Hello, API!");
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
curl http://localhost:3000
```

## 出力結果
```
Hello, API!
```
