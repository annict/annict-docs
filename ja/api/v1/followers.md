# GET /v1/followers

Annictに登録されているユーザのフォロワー情報を取得することができます。

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
$ curl -X GET https://api.annict.com/v1/followers?access_token=(access_token)&filter_username=shimbaco&per_page=2
```

```json
{
  "users": [
    {
      "id": 7,
      "username": "akirafukuoka",
      "name": "akirafukuoka",
      "description": "FICC inc. http://www.ficc.jp  クリエイティブディレクター。RAW-Fi http://raw-fi.com  @raw_fi もよろしくお願いします。",
      "url": null,
      "avatar_url": "https://api-assets.annict.com/paperclip/profiles/6/tombo_avatars/master/480862747fc5f7152a031e24f0c0374dc71c539a.jpg?1431596794",
      "background_image_url": "https://api-assets.annict.com/paperclip/profiles/6/tombo_background_images/master/7e258e0189e9ee38f4dc0c57b2c9f6b39dd2cd95.jpg?1431596795",
      "records_count": 260,
      "created_at": "2014-03-10T04:11:54.000Z"
    },
    {
      "id": 8,
      "username": "310u8",
      "name": "Daisuke Nagai",
      "description": "歌って踊れるWebデザイナーです",
      "url": null,
      "avatar_url": "https://api-assets.annict.com/paperclip/profiles/7/tombo_avatars/master/cd7b66919fea1952e63855632665812839e2a394.jpg?1428129527",
      "background_image_url": "https://api-assets.annict.com/paperclip/profiles/7/tombo_avatars/master/cd7b66919fea1952e63855632665812839e2a394.jpg?1428129527",
      "records_count": 739,
      "created_at": "2014-03-10T04:11:55.000Z"
    }
  ],
  "total_count": 191,
  "next_page": 2,
  "prev_page": null
}
```
