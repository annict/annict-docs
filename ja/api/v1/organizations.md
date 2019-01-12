# GET /v1/organizations

Annictに登録されている団体情報を取得することができます。


## フィールド

| 名前 | 概要 |
| --- | --- |
| id | ID |
| name | 名前 |
| name_kana | 名前 (かな表記) |
| name_en | 名前 (英語表記) |
| url | 公式サイト等のURL |
| url_en | 公式サイト等のURL (英語圏向け) |
| wikipedia_url | WikipediaのURL |
| wikipedia_url_en | WikipediaのURL (英語圏向け) |
| twitter_username | Twitterアカウントのusername |
| twitter_username_en | Twitterアカウントのusername (英語圏向け) |
| favorite_organizations_count | お気に入りに入れている人の数 |
| staffs_count | スタッフとして登録されている作品の数 |


## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,name |
| filter_ids | 団体をIDで絞り込みます。 | filter_ids=1,2,3 |
| filter_name | 団体を名前で絞り込みます。 | filter_name=株式会社 |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | 団体をIDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/organizations?access_token=(access_token)&filter_ids=3
```

```json
{
  "organizations": [
    {
      "id": 3,
      "name": "P.A.WORKS",
      "name_kana": "ぴーえーわーくす",
      "name_en": "P.A.WORKS",
      "url": "http://www.pa-works.jp/",
      "url_en": "https://www.pa-works.jp/en/",
      "wikipedia_url": "https://ja.wikipedia.org/wiki/%E3%83%94%E3%83%BC%E3%82%A8%E3%83%BC%E3%83%AF%E3%83%BC%E3%82%AF%E3%82%B9",
      "wikipedia_url_en": "",
      "twitter_username": "PAWORKS_info",
      "twitter_username_en": "PAWORKS_eng",
      "favorite_organizations_count": 81,
      "staffs_count": 23
    }
  ],
  "total_count": 1,
  "next_page": null,
  "prev_page": null
}
```
