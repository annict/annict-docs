# 概要

## エンドポイント

GraphQL APIのエンドポイントは下記になります。

```
https://api.annict.com/graphql
```


## GraphQL APIにリクエストを送信する

AnnictのGraphQL APIにリクエストを送信するときは、[REST API](../v1/overview.md)と同様にアクセストークンを付加する必要があります。アクセストークンの取得方法もREST APIと同様です。[認証ページ](../v1/authentication.md)をご確認ください。

GraphQLの実行はコマンドラインやGraphQLクライアントを使用して行うことができます。
コマンドラインから実行する場合は、以下のような `curl` コマンドを実行します。

```
$ curl https://api.annict.com/graphql \
-H "Authorization: bearer (アクセストークン)" \
-X POST \
-d "query=query { viewer { name } }"
```

`query` パラメータに `query { viewer { name } }` というクエリを付加してPOSTリクエストを送っています。
上記コマンドを実行すると下記のようなJSONデータが返ります。

```json
{"data":{"viewer":{"name":"Koji Shimba"}}}
```

以上のようにコマンドラインからリクエストを送信することができますが、GraphQLクライアントを使用したほうが便利です。
[GraphiQL](https://github.com/graphql/graphiql) というブラウザベースで動作するIDEをElectronでラップした https://github.com/skevy/graphiql-app というアプリがMac等で動かすことができます。

GraphiQL.appやAnnictのGraphQL APIからのデータ取得方法をQiitaにまとめているので、良ければそちらもご覧ください。

[AnnictのGraphQL APIを使ってアニメデータを取得しよう \- Qiita](http://qiita.com/shimbaco/items/e3f2f8650b08e1e060bd)


## よくありそうな質問

#### `annictId` と `id` の違いは？

このGraphQL APIドキュメントにはよく「Annict ID」という単語が出てきます。
Annict IDとは、Annictのデータベース内の各テーブルに存在する固有のIDになります。
例えば作品「[エロマンガ先生](https://annict.com/works/4714)」のAnnict IDは「4714」になります。
(Railsがデフォルトで提供するプライマリキーです。)

対して `id` とは全てのオブジェクトにおいて固有のIDになります。
Annict IDは各テーブルに同じ値が存在し得ますが、`id` には全テーブル内の全データごとに固有の値が設定されています。
