# GET /v1/series

Annictに登録されているシリーズ情報を取得することができます。


## フィールド

| 名前 | 概要 |
| --- | --- |
| id | ID |
| name | 名前 |
| name_ro | 名前 (ローマ字表記) |
| name_en | 名前 (英語表記) |


## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,name |
| filter_ids | シリーズをIDで絞り込みます。 | filter_ids=1,2,3 |
| filter_name | シリーズを名前で絞り込みます。 | filter_name=株式会社 |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | シリーズをIDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/series?access_token=(access_token)&filter_ids=65
```

```json
{
  "series": [
    {
      "id": 65,
      "name": "ソードアート・オンライン",
      "name_ro": "Sword Art Online",
      "name_en": "Sword Art Online"
    }
  ],
  "total_count": 1,
  "next_page": null,
  "prev_page": null
}
```
