# GET /v1/reviews

作品へのレビューを取得することができます。

## フィールド

| 名前 | 概要 |
| --- | --- |
| id | レビューID |
| title | **[非推奨]** レビュータイトル |
| body | レビュー本文 |
| rating_animation_state | レビューしたときに付けられたレーティング (作画)。`bad` `average` `good` `great` の4種類のうち1つが入っています。 |
| rating_music_state | レビューしたときに付けられたレーティング (音楽)。`bad` `average` `good` `great` の4種類のうち1つが入っています。 |
| rating_story_state | レビューしたときに付けられたレーティング (ストーリー)。`bad` `average` `good` `great` の4種類のうち1つが入っています。 |
| rating_character_state | レビューしたときに付けられたレーティング (キャラクター)。`bad` `average` `good` `great` の4種類のうち1つが入っています。 |
| rating_overall_state | レビューしたときに付けられたレーティング (全体)。`bad` `average` `good` `great` の4種類のうち1つが入っています。 |
| likes_count | Likeされた数 |
| impressions_count | PV数 |
| created_at | レビューが投稿された日時 |
| modified_at | レビューが編集された日時 |
| user | このレビューを投稿した利用者の情報 |
| work | このレビューが紐づく作品情報。取得できるフィールドは [Works](works.md) と同じです。 |

## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,title |
| filter_ids | レビューをレビューIDで絞り込みます。 | filter_ids=1,2,3 |
| filter_work_id | レビューを作品IDで絞り込みます。 | filter_work_id=1111 |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | レビューをレビューIDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |
| sort_likes_count | レビューをLikeされた数で並び替えます。`asc` または `desc` が指定できます。 | sort_likes_count=desc |


## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/records?filter_work_id=3994&access_token=(access_token)
```

```json
{
    "reviews": [
        {
            "id": 594,
            "title": "あぁ^～心がぴょんぴょんするんじゃぁ^～",
            "body": "みんなかわいい",
            "rating_animation_state": "good",
            "rating_music_state": "good",
            "rating_story_state": "good",
            "rating_character_state": "great",
            "rating_overall_state": "great",
            "likes_count": 0,
            "impressions_count": 1,
            "modified_at": null,
            "created_at": "2017-06-24T18:51:35.075Z",
            "user": {
                "id": 2,
                "username": "shimbaco",
                "name": "Koji Shimba",
                "description": "アニメ好きが高じてこのサービスを作りました。聖地巡礼を年に数回しています。",
                "url": "http://shimba.co",
                "avatar_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_avatars/master/d8af7adc8122c96ba7639218fd8b5ede332d42f2.jpg?1431357292",
                "background_image_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_background_images/master/ee15d577fb2f2d61bdaf700cfab894b286a5762d.jpg?1486753229",
                "records_count": 1906,
                "created_at": "2014-03-02T15:38:40.000Z"
            },
            "work": {
                "id": 3994,
                "title": "ご注文はうさぎですか？",
                "title_kana": "ごちゅうもんはうさぎですか",
                "media": "tv",
                "media_text": "TV",
                "released_on": "2014-04-10",
                "released_on_about": "",
                "official_site_url": "http://www.gochiusa.com/",
                "wikipedia_url": "http://ja.wikipedia.org/wiki/%E3%81%94%E6%B3%A8%E6%96%87%E3%81%AF%E3%81%86%E3%81%95%E3%81%8E%E3%81%A7%E3%81%99%E3%81%8B%3F#.E3.83.86.E3.83.AC.E3.83.93.E3.82.A2.E3.83.8B.E3.83.A1",
                "twitter_username": "usagi_anime",
                "twitter_hashtag": "gochiusa",
                "images": {
                    "recommended_url": "https://twitter.com/usagi_anime/profile_image?size=bigger",
                    "facebook": {
                        "og_image_url": ""
                    },
                    "twitter": {
                        "mini_avatar_url": "https://twitter.com/usagi_anime/profile_image?size=mini",
                        "normal_avatar_url": "https://twitter.com/usagi_anime/profile_image?size=normal",
                        "bigger_avatar_url": "https://twitter.com/usagi_anime/profile_image?size=bigger",
                        "original_avatar_url": "https://twitter.com/usagi_anime/profile_image?size=original",
                        "image_url": ""
                    }
                },
                "episodes_count": 12,
                "watchers_count": 1463,
                "season_name": "2014-spring",
                "season_name_text": "2014年春"
            }
        },
        ...
    ],
    "total_count": 6,
    "next_page": null,
    "prev_page": null
}
```
