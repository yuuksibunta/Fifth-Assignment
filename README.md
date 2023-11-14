# 1.URL
* URLとは
・・・ホームページの置いてある場所やファイル名を示す情報
  | 要素 | 説明 | 
  |----------------|---------------|
  |プロトコル|対象となる事項を実行するためのルール|
  | スキーム | プロトコルというルールを規定するもの |
  |ホスト名|ネットワークに接続されたホスト（機器やサーバー）の名前|
  | トップレベルドメイン|インターネット上で登録されている組織の種別を表す要素|
  |セカンドレベルドメイン| ドメインの中で2番目に属しているドメイン(※トップドメルトメインによって変わる）|
  |ディレクトリ|Webサイトの中でどのセクションが表示されているかを表すもの|
  |ファイル名|URLの末尾に配置される一番小さなファイル|
  
   ![image](https://github.com/yuuksibunta/Fifth-Assignment/assets/148073110/2b7eae84-6793-4ba9-8c23-3248c54a9c93)

 ***

 
# 2.クエリ文字列
* クエリ文字列とは・・・サーバに情報を送るために、URLの末尾に付け足す文字列のこと
  > `https://○○○○.jp/?×=△△ の『?×=△△』の部分`
* クエリ文字列の種類（2種類）
  | 名称 | 用途 |
  |----------------|---------------|
  |パッシパラメーター|ウェブサイトのアクセス解析のため（表示されるコンテンツには影響なし）|
  |アクティブパラメーター|パラメーターを付け加えて、ウェブサイトの表示内容を変更する（表示されるコンテンツに影響あり）|
 ### パス変数（パスパラメーター）とは何か
　→URLの一部としてリクエストに含まれ、リソースやエンドポイントに対して情報を送信するために使用されるもの
   > `https://example.com/users/:id　の:idの部分`
 ### クエリ文字列とパス変数(パスパラメーター）の違いは？
 | 名称 | 概要 | 見た目 |
  |------|-----------------------------------------------|---------------------------------------------------|
  |クエリ文字列|特定のものに条件を追加する際に必要なものなのか|`https://example.com/search?query=programming`  |
  |パス変数（パスパラメーター)|特定のものを判別するのか際に必要なもの|`https://example.com/users/:id`  |

  ***

  
 # 3.HTTPメソッド
 * HTTPメソッドは、HTTPプロトコルを使用してクライアントとサーバー間で通信する際に使用されるコマンドまたはアクションのこと

| メソッド名 | 役割 |例|
|------------|------|------------|
| GET        | サーバーからリソース（データや文書）を取得するために使用 |GET /example/resource HTTP/1.1|
| POST       | サーバーに新しいデータを送信するために使用 |POST /example/resource HTTP/1.1 Content-Type: application/json|
| PUT        | サーバー上の既存のデータを更新または新しいデータを作成するために使用 |PUT /example/resource/123 HTTP/1.1Content-Type: application/json|
| PATCH      | サーバー上のリソースの一部分を更新するために使用 |PATCH /example/resource/123 HTTP/1.1 Content-Type: application/json|
| DELETE     | サーバー上のリソースを削除するために使用 |DELETE /example/resource/123 HTTP/1.1|
 
 ****注：HTTPのバージョンの、HTTP/1.1とHTTP/2は現在でも広く使用されているが、HTTP/3は将来のウェブ通信の進化を担う可能性あり。****

***

# 4. リクエストヘッダー
   * リクエストヘッダーとは・・・HTTPリクエストに含まれるメタデータや追加の情報をサーバーに伝えるための部分
     
  【イメージ図】
     
  ![image](https://github.com/yuuksibunta/Fifth-Assignment/assets/148073110/164df5e8-7e09-4be7-bbb1-f30e3059d3e8)

　【HTTPリクエストヘッダーの例】
```
GET /example/page HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8
Accept-Language: en-US,en;q=0.9
Referer: https://www.referer-example.com/page
Cookie: user_session=abc123; preferences=dark-theme
```

  →　リクエストヘッダーに入るのは、WebブラウザからWebサーバーに伝えたい情報

***

# 5.HTTPステータスコード
* HTTPステータスコードとは・・・HTTPリクエストの結果を示す3桁の数字　　

 【HTTPステータスコードの種類】
 　
| コード | 意味 |
| ---- | ---- |
| 200 |　成功 |
| 201 |　Created"（作成成功） |
| 307 |　リダイレクト,リクエストメソッドを維持してリダイレクト |
| 400 |　Bad Request,リクエストの内容が変,クライアントエラー,送る側の問題 |
| 404 |　Not Found,リソースが見つからない |
| 500 |　Internal Server Error,サーバーエラー,サーバー側の問題 |

***

# 6.レスポンスヘッダー
* レスポンスヘッダーとは・・・HTTPレスポンスを構成する部品のひとつであり、ステータスラインに書ききれない情報が書かれている

  【イメージ図】

  ![image](https://github.com/yuuksibunta/Fifth-Assignment/assets/148073110/fcfd02cd-f2cf-46ac-8571-d97c98b82d23)

  →　ステータスライン（HTTP/1.1 200 OK￥r￥n..など）に書ききれない情報が書かれている。

***

# 7.レスポンスボディ
* レスポンスボディとは・・・HTTPレスポンスを構成する部品のひとつであり、要求したファイルの中身が書いてある場所

  【HTTPレスポンスの一部を示す例】
```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 128

<!DOCTYPE html>
<html>
<head>
    <title>Example Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
</body>
</html>
```

　→　レスポンスボディに含まれるデータのフォーマットは、Content-Typeヘッダーによって示されます。HTML、XML、JSON、画像、テキストなどさまざまなフォーマットがあります。

***

# 8.JSON（JavaScriptObjectNotation)
* JSONとは・・・ファイルの書き方のルールの一つ

 【JSONの例】
``` json
{
  "person": {
    "name": "田中　五右衛門",
    "age": 29,
    "isStudent": false,
    "address": {
      "city": "東京",
    },
    "hobbies": ["ランニング", "料理"]
  }
}
```
上記のコードは、"person"（人物）というオブジェクトを表現している。
　
 * "person": キー名で、これは人物の情報を含むオブジェクトを示す
 * "name": 田中五右衛門さんの名前を表す
 * "age": 29歳であることを示す
 * "isStudent": 学生でないことを示す論理値 (false) 。
 * "address": 住所に関するオブジェクトで、その中に都市名 ("東京") を含む。
 * hobbies": 趣味に関する配列で、"ランニング"と"料理"の２つの要素が含まれている。

→ ウェブアプリケーションがこのデータを受け取った場合、それを解析してユーザーに対して表示することができる。
JSONはシンプルで理解しやすく、多くのプログラミング言語でサポートされている。また、Web APIの応答や構成ファイル、データベースのデータのやり取りなど、さまざまな用途で利用されている。

***

## 参考文献


- [MDN](https://developer.mozilla.org/ja/docs/Web)
- [わわわ](https://wa3.i-3-i.info/)
- [デジハリONLINE](https://online.dhw.co.jp/kuritama/query-string/ "クエリ文字列（URLパラメーター）とは？ Webサービス上の用途とその役割")
- [Zenn](https://zenn.dev/eri_agri/articles/859a3362db8386 "パスパラメータとクエリパラメータの違い")
- [Qiita](https://qiita.com/Qiita/items/c686397e4a0f4f11683d "Markdown記法 チートシート")
- [Techpit](https://techpit-market.gitbook.io/host-guide/4/markdown "見やすい文章を書くためのマークダウンの書き方")

  





 


  

