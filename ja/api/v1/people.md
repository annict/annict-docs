# GET /v1/people

Annictに登録されている人物情報を取得することができます。


## フィールド

| 名前 | 概要 |
| --- | --- |
| id | ID |
| name | 名前 |
| name_kana | 名前 (かな表記) |
| name_en | 名前 (英語表記) |
| nickname | ニックネーム |
| nickname_en | ニックネーム (英語表記) |
| gender_text | 性別 |
| url | 公式サイト等のURL |
| url_en | 公式サイト等のURL (英語圏向け) |
| wikipedia_url | WikipediaのURL |
| wikipedia_url_en | WikipediaのURL (英語圏向け) |
| twitter_username | Twitterアカウントのusername |
| twitter_username_en | Twitterアカウントのusername (英語圏向け) |
| birthday | 誕生日 |
| blood_type | 血液型 |
| height | 身長 |
| favorite_people_count | お気に入りに入れている人の数 |
| casts_count | キャストとして登録されている作品の数 |
| staffs_count | スタッフとして登録されている作品の数 |
| prefecture | 出身地 |


## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,name |
| filter_ids | 人物をIDで絞り込みます。 | filter_ids=1,2,3 |
| filter_name | 人物を名前で絞り込みます。 | filter_name=井上 |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | 人物をIDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/people?access_token=(access_token)&filter_ids=7118
```

```json
{
  "people": [
    {
      "id": 7118,
      "name": "水瀬いのり",
      "name_kana": "みなせいのり",
      "name_en": "Minase, Inori",
      "nickname": "いのりん、いのすけ",
      "nickname_en": "",
      "gender_text": "女性",
      "url": "http://axl-one.com/talent/minase.html",
      "url_en": "",
      "wikipedia_url": "https://ja.wikipedia.org/wiki/%E6%B0%B4%E7%80%AC%E3%81%84%E3%81%AE%E3%82%8A",
      "wikipedia_url_en": "",
      "twitter_username": "inoriminase",
      "twitter_username_en": "",
      "birthday": "1995-12-02",
      "blood_type": "b",
      "height": 154,
      "favorite_people_count": 74,
      "casts_count": 58,
      "staffs_count": 0,
      "prefecture": {
        "id": 13,
        "name": "東京都"
      }
    }
  ],
  "total_count": 1,
  "next_page": null,
  "prev_page": null
}
```
