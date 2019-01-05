# GET /v1/staffs

Annictに登録されているスタッフ情報を取得することができます。


## フィールド

| 名前 | 概要 |
| --- | --- |
| id | ID |
| name | 名前 |
| name_en | 名前 (英語表記) |
| role_text | 担当。主要な担当名 (監督やアニメーション制作など) が登録されています。 |
| role_other | その他の担当 |
| role_other_en | その他の担当 (英語表記) |
| sort_number | ソート番号 |
| work | 紐づく作品情報。取得できるフィールドは [Works](works.md) と同じです。 |
| person または organization | 紐づく人物または団体情報。取得できるフィールドは [People](people.md) または [Organizations](organizations.md) と同じです。 |
 

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
$ curl -X GET https://api.annict.com/v1/staffs?access_token=(access_token)&filter_ids=35319
```

```json
{
  "staffs": [
    {
      "id": 35319,
      "name": "京都アニメーション",
      "name_en": "",
      "role_text": "アニメーション制作",
      "role_other": "",
      "role_other_en": "",
      "sort_number": 200,
      "work": {
        "id": 4308,
        "title": "響け！ユーフォニアム",
        ...
      },
      "organization": {
        "id": 74,
        "name": "京都アニメーション",
        ...
      }
    }
  ],
  "total_count": 1,
  "next_page": null,
  "prev_page": null
}
```
