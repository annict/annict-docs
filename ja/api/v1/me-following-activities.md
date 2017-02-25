# GET /v1/me/following_activities

自分がフォローしているユーザのアクティビティを取得することができます。

## フィールド

取得できるフィールドは [Activities](activities.md) と同じです。


## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,title |
| filter_actions | アクションで絞り込みます。 | filter_actions=create_record,create_multiple_records |
| filter_muted | ミュート機能でミュートしているユーザを除外するかどうかを指定します。 `true` で除外、 `false` で除外しないようにできます。デフォルトは `true` (除外する) です。 | filter_muted=false |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | IDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/me/following_activities?access_token=(access_token)&sort_id=desc&per_page=1
```

```json
{
  "activities": [
    {
      "id": 1504708,
      "user": {
        "id": 2,
        "username": "shimbaco",
        "name": "Koji Shimba",
        "description": "アニメ好きが高じてこのサービスを作りました。聖地巡礼を年に数回しています。",
        "url": "http://shimba.co",
        "avatar_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_avatars/master/d8af7adc8122c96ba7639218fd8b5ede332d42f2.jpg?1431357292",
        "background_image_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_background_images/master/ee15d577fb2f2d61bdaf700cfab894b286a5762d.jpg?1486753229",
        "records_count": 2369,
        "created_at": "2014-03-02T15:38:40.000Z"
      },
      "action": "create_record",
      "created_at": "2017-02-22T13:24:44.761Z",
      "work": {
        "id": 5036,
        "title": "小林さんちのメイドラゴン",
        "title_kana": "こばやしさんちのめいどらごん",
        "media": "tv",
        "media_text": "TV",
        "released_on": "",
        "released_on_about": "",
        "official_site_url": "http://maidragon.jp/",
        "wikipedia_url": "https://ja.wikipedia.org/wiki/%E5%B0%8F%E6%9E%97%E3%81%95%E3%82%93%E3%81%A1%E3%81%AE%E3%83%A1%E3%82%A4%E3%83%89%E3%83%A9%E3%82%B4%E3%83%B3",
        "twitter_username": "maidragon_anime",
        "twitter_hashtag": "maidragon",
        "episodes_count": 7,
        "watchers_count": 448,
        "season_name": "2017-winter",
        "season_name_text": "2017年冬"
      },
      "episode": {
        "id": 89678,
        "number": "6",
        "number_text": "#6",
        "sort_number": 60,
        "title": "お宅訪問！(してないお宅もあります)",
        "records_count": 89,
        "record_comments_count": 24
      },
      "record": {
        "id": 864718,
        "comment": "",
        "rating": null,
        "is_modified": false,
        "likes_count": 0,
        "comments_count": 0,
        "created_at": "2017-02-22T13:24:39.353Z"
      }
    }
  ],
  "total_count": 138030,
  "next_page": 2,
  "prev_page": null
}
```
