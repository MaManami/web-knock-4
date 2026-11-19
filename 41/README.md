# 41. シンプルなHTTPサーバ
### Node.jsとExpressを使い，「Hello, API!」と返すだけのHTTPサーバを実装すること．

#### ソースコード(.js)
```
const express = require("express");

const app = express();
const port = 3000;

// ルート（"/"）にアクセスがあったときの処理
app.get("/", (req, res) => {
  res.send("Hello, API!");
});

// サーバーを起動する
app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
```

#### curlコマンド
```
curl http://localhost:3000
```

#### 出力結果
```
Hello, API!
```
