# GET /v1/following

Annictに登録されているユーザのフォロー情報を取得することができます。

## フィールド

[GET /v1/users](users.md) のフィールドと同じです。


## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,username |
| filter_user_id | ユーザIDで絞り込みます。 | filter_user_id=2 |
| filter_username | ユーザ名で絞り込みます。 | filter_username=shimbaco |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | IDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/following?access_token=(access_token)&filter_username=shimbaco&per_page=2
```

```json
{
  "users": [
    {
      "id": 3,
      "username": "builtlast",
      "name": "岩永勇輝 (Creasty)",
      "description": "Web やってる大学生\nプログラミングとかデザインとか\n価値を生み出せるようになりたい\n\nアルバイト@FICC\n\nC / Obj-C / Ruby / Haskell / PHP / CoffeeScript / VimScript / Photoshop / Illustrator",
      "url": null,
      "records_count": 0,
      "created_at": "2014-03-04T09:32:25.000Z"
    },
    {
      "id": 4,
      "username": "pataiji",
      "name": "PATAIJI",
      "description": "FICC inc.ベースやってます。カブに乗ってます。AWSすごい良い。Railsすごい楽。",
      "url": null,
      "records_count": 0,
      "created_at": "2014-03-04T09:32:28.000Z"
    }
  ],
  "total_count": 4214,
  "next_page": 2,
  "prev_page": null
}
```
