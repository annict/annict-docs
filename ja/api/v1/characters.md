# GET /v1/characters

Annictに登録されているキャラクター情報を取得することができます。


## フィールド

| 名前 | 概要 |
| --- | --- |
| id | ID |
| name | 名前 |
| name_kana | 名前 (かな表記) |
| name_en | 名前 (英語表記) |
| nickname | ニックネーム |
| nickname_en | ニックネーム (英語表記) |
| birthday | 誕生日 |
| birthday_en | 誕生日 (英語表記) |
| age | 年齢 |
| age_en | 年齢 (英語表記) |
| blood_type | 血液型 |
| blood_type_en | 血液型 (英語表記) |
| height | 身長 |
| height_en | 身長 (英語表記) |
| weight | 体重 |
| weight_en | 体重 (英語表記) |
| nationality | 国籍 |
| nationality_en | 国籍 (英語表記) |
| occupation | 肩書き |
| occupation_en | 肩書き (英語表記) |
| description | キャラ紹介 |
| description_en | キャラ紹介 (英語表記) |
| description_source | キャラ紹介の引用元 |
| description_source_en | キャラ紹介の引用元 (英語表記) |
| favorite_characters_count | お気に入りに入れている人の数 |
| series | 紐づくシリーズ情報。取得できるフィールドは [Series](series.md) と同じです。 |
 

## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,name |
| filter_ids | キャラクターをIDで絞り込みます。 | filter_ids=1,2,3 |
| filter_name | キャラクターを名前で絞り込みます。 | filter_name=株式会社 |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | キャラクターをIDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/characters?access_token=(access_token)&filter_ids=7510
```

```json
{
  "characters": [
    {
      "id": 7510,
      "name": "岡部倫太郎",
      "name_kana": "おかべりんたろう",
      "name_en": "Okabe, Rintarou",
      "kind": "STEINS;GATE",
      "nickname": "鳳凰院凶真、おかりん",
      "nickname_en": "Hououin, Kyouma",
      "birthday": "12月14日",
      "birthday_en": "December 14",
      "age": "18歳",
      "age_en": "18",
      "blood_type": "A型",
      "blood_type_en": "A",
      "height": "177 cm",
      "height_en": "177 cm",
      "weight": "59 kg",
      "weight_en": "59 kg",
      "nationality": "日本",
      "nationality_en": "Japan",
      "occupation": "狂気のマッドサイエンティスト",
      "occupation_en": "Crazy Mad Scientist",
      "description": "未来ガジェット研究所のラボメンNo.001にして、ラボの創設者。東京電機大学1年生。まゆりや橋田からは「オカリン」と呼ばれている。実家は青果店。",
      "description_en": "",
      "description_source": " Wikipedia【STEINS;GATEの登場人物】",
      "description_source_en": "",
      "favorite_characters_count": 13,
      "series": {
        "id": 50,
        "name": "Steins;Gate",
        "name_ro": "",
        "name_en": ""
      }
    }
  ],
  "total_count": 1,
  "next_page": null,
  "prev_page": null
}
```
