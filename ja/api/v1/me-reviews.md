# POST /v1/me/reviews

作品へのレビューが投稿できます。

**このリクエストには `write` スコープが必要になります。**

## パラメータ

| 名前 | 概要 | データ例 |
| --- | --- | --- |
| work_id | **[必須]** 作品ID | 3994 |
| title | **[非推奨]** タイトル。現在このプロパティに入力された文字列は感想にマージされます。 | あぁ^～心がぴょんぴょんするんじゃぁ^～ |
| body | **[必須]** 感想 | 僕は、リゼちゃん！◯（ ´∀｀ ）◯ |
| rating_animation_state | レーティング (映像)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_music_state | レーティング (音楽)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_story_state | レーティング (ストーリー)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_character_state | レーティング (キャラクター)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_overall_state | レーティング (全体)。`bad` `average` `good` `great` が入力できます。 | great |
| share_twitter | 記録をTwitterにシェアするかどうか。`true` または `false` が入力できます。指定しなかったときは `false` (シェアしない) になります。 | true |
| share_facebook | 記録をFacebookにシェアするかどうか。`true` または `false` が入力できます。指定しなかったときは `false` (シェアしない) になります。 | true |


## リクエスト例

```
$ curl -X POST "https://api.annict.com/v1/me/reviews?work_id=3994&title=あぁ^～心がぴょんぴょんするんじゃぁ^～&body=みんなかわいい&rating_animation_state=good&rating_music_state=good&rating_story_state=good&rating_character_state=great&rating_overall_state=great&access_token=(access_token)"
```

```json
{
    "id": 595,
    "title": "",
    "body": "あぁ^～心がぴょんぴょんするんじゃぁ^～\n\nみんなかわいい",
    "rating_animation_state": "good",
    "rating_music_state": "good",
    "rating_story_state": "good",
    "rating_character_state": "great",
    "rating_overall_state": "great",
    "likes_count": 0,
    "impressions_count": 0,
    "modified_at": null,
    "created_at": "2017-06-24T18:59:57.192Z",
    "user": {
        "id": 2,
        "username": "shimbaco",
        "name": "Koji Shimba",
        "description": "",
        "url": null,
        "avatar_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_avatars/master/d8af7adc8122c96ba7639218fd8b5ede332d42f2.jpg?1431357292",
        "background_image_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_background_images/master/ee15d577fb2f2d61bdaf700cfab894b286a5762d.jpg?1486753229",
        "records_count": 123,
        "created_at": "2016-05-03T19:06:59.929Z"
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
}
```


# PATCH /v1/me/reviews/:id

作成したレビューを編集することができます。

**このリクエストには `write` スコープが必要になります。**

## パラメータ

| 名前 | 概要 | データ例 |
| --- | --- | --- |
| id | **[必須]** 記録ID | 1016 |
| title | **[必須]** タイトル | あぁ^～心がぴょんぴょんするんじゃぁ^～ |
| body | **[必須]** 感想 | 僕は、リゼちゃん！◯（ ´∀｀ ）◯ |
| rating_animation_state | **[必須]** レーティング (映像)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_music_state | **[必須]** レーティング (音楽)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_story_state | **[必須]** レーティング (ストーリー)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_character_state | **[必須]** レーティング (キャラクター)。`bad` `average` `good` `great` が入力できます。 | great |
| rating_overall_state | **[必須]** レーティング (全体)。`bad` `average` `good` `great` が入力できます。 | great |
| share_twitter | 記録をTwitterにシェアするかどうか。`true` または `false` が入力できます。指定しなかったときは `false` (シェアしない) になります。 | true |
| share_facebook | 記録をFacebookにシェアするかどうか。`true` または `false` が入力できます。指定しなかったときは `false` (シェアしない) になります。 | true |


## リクエスト例

```
$ curl -X PATCH "https://api.annict.com/v1/me/reviews/595?title=あぁ^～心がぴょんぴょんするんじゃぁ^～&body=みんなかわいい！！&rating_animation_state=good&rating_music_state=good&rating_story_state=good&rating_character_state=great&rating_overall_state=great&access_token=(access_token)"
```

```json
{
    "id": 595,
    "title": "あぁ^～心がぴょんぴょんするんじゃぁ^～",
    "body": "みんなかわいい！！",
    "rating_animation_state": "good",
    "rating_music_state": "good",
    "rating_story_state": "good",
    "rating_character_state": "great",
    "rating_overall_state": "great",
    "likes_count": 0,
    "impressions_count": 1,
    "modified_at": "2017-06-24T19:07:46.257Z",
    "created_at": "2017-06-24T18:59:57.192Z",
    "user": {
        "id": 2,
        "username": "shimbaco",
        "name": "Koji Shimba",
        "description": "",
        "url": null,
        "avatar_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_avatars/master/d8af7adc8122c96ba7639218fd8b5ede332d42f2.jpg?1431357292",
        "background_image_url": "https://api-assets.annict.com/paperclip/profiles/1/tombo_background_images/master/ee15d577fb2f2d61bdaf700cfab894b286a5762d.jpg?1486753229",
        "records_count": 123,
        "created_at": "2016-05-03T19:06:59.929Z"
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
}
```


# DELETE /v1/me/reviews/:id

作成した記録を削除することができます。

**このリクエストには `write` スコープが必要になります。**

## パラメータ

| 名前 | 概要 | データ例 |
| --- | --- | --- |
| id | **[必須]** 記録ID | 595 |


## リクエスト例

```
$ curl -X DELETE "https://api.annict.com/v1/me/reviews/595?access_token=(access_token)"
```

```
HTTP/1.1 204 No Content
```
