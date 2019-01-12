# GET /v1/casts

Annictに登録されているキャスト情報を取得することができます。


## フィールド

| 名前 | 概要 |
| --- | --- |
| id | ID |
| name | 名前 |
| name_en | 名前 (英語表記) |
| sort_number | ソート番号 |
| work | 紐づく作品情報。取得できるフィールドは [Works](works.md) と同じです。 |
| character | 紐づくキャラクター情報。取得できるフィールドは [Characters](characters.md) と同じです。 |
| person | 紐づく人物情報。取得できるフィールドは [People](people.md) と同じです。 |
 

## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,name |
| filter_ids | IDで絞り込みます。 | filter_ids=1,2,3 |
| filter_work_id | 作品IDで絞り込みます。 | filter_work_id=1111 |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | IDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |
| sort_sort_number | ソート用の番号で並び替えます。`asc` または `desc` が指定できます。 | sort_sort_number=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/casts?access_token=(access_token)&filter_ids=43414
```

```json
{
  "casts": [
    {
      "id": 43414,
      "name": "東山奈央",
      "name_en": "Touyama, Nao",
      "sort_number": 10,
      "work": {
        "id": 5459,
        "title": "ゆるキャン△",
        ...
      },
      "character": {
        "id": 32268,
        "name": "志摩リン",
        ...
      },
      "person": {
        "id": 1411,
        "name": "東山奈央",
        ...
      }
    }
  ],
  "total_count": 1,
  "next_page": null,
  "prev_page": null
}
```
