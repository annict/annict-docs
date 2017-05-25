# 概要

**AnnictのGraphQL APIはまだ公開されていません。このドキュメントに書かれていることはまだできないのでご注意下さい**

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

graphiql-appやAnnictのGraphQL APIからのデータ取得方法をQiitaにまとめているので、良ければそちらもご覧ください。


## よくありそうな質問

#### 「Annict ID」とは？

このGraphQL APIドキュメントにはよく「Annict ID」という単語が出てきます。
Annict IDとは、Annictのデータベース内の各テーブルに存在する固有のIDになります。
例えば作品「[エロマンガ先生](https://annict.com/works/4714)」のAnnict IDは「4714」になります。
(Railsがデフォルトで提供するプライマリキーです。)
