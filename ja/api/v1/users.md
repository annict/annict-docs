# GET /v1/users

Annictに登録されているユーザ情報を取得することができます。

## フィールド

| 名前 | 概要 |
| --- | --- |
| id | ユーザID |
| username | URLなどで使用されているユーザ名 |
| name | ユーザの名前 |
| description | プロフィール |
| url | ユーザのURL |
| records_count | 記録数 |
| created_at | ユーザ登録した日時 |


## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,username |
| filter_ids | ユーザをIDで絞り込みます。 | filter_ids=1,2,3 |
| filter_usernames | ユーザをユーザ名で絞り込みます。 | filter_usernames=shimbaco,datekoichi |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | ユーザをIDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/users?access_token=(access_token)&filter_usernames=shimbaco
```

```json
{
  "users": [
    {
      "id": 2,
      "username": "shimbaco",
      "name": "Koji Shimba",
      "description": "アニメ好きが高じてこのサービスを作りました。聖地巡礼を年に数回しています。",
      "url": "http://shimba.co",
      "records_count": 2369,
      "created_at": "2014-03-02T15:38:40.000Z"
    }
  ],
  "total_count": 1,
  "next_page": null,
  "prev_page": null
}
```
