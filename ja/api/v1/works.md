# GET /v1/works

Annictに登録されている作品情報を取得することができます。

## フィールド

| 名前 | 概要 |
| --- | --- |
| id | 作品のID |
| title | 作品のタイトル |
| title_kana | 作品タイトルの読み仮名 |
| media | リリース媒体 `tv, ova, movie, web, other` |
| media_text | リリース媒体 (表記用) `TV, OVA, 映画, Web, その他` |
| season_name | リリース時期 |
| season_name_text | リリース時期 (表記用) |
| released_on | リリース日 |
| released_on_about | 未確定な大体のリリース日 |
| official_site_url | 公式サイトのURL |
| wikipedia_url | WikipediaのURL |
| twitter_username | 公式Twitterアカウントのusername |
| twitter_hashtag | Twitterの作品に関するハッシュタグ |
| mal_anime_id | MyAnimeListの作品ID |
| images.facebook.og_image_url | `official_site_url` のページで取得できる `og:image` のURL |
| images.twitter.(mini/normal/bigger/original)_avatar_url | Twitterアカウントのアバター画像。`mini`, `normal`, `bigger`, `original` の4種類のサイズがあります |
| images.twitter.image_url | `official_site_url` のページで取得できる `twitter:image` のURL |
| images.recommended_url | `facebook.og_image_url`, `twitter.bigger_avatar_url`, `twitter.image_url` のうち、解像度が一番大きい画像のURL。扱いやすい画像のURLが高確率で格納されるプロパティになります |
| episodes_count | エピソード数 |
| watchers_count | 見てる / 見たい / 見た人の数 |
| reviews_count | レビュー数 |
| no_episodes | エピソードが存在しない作品かどうか。例えば映画はエピソードが存在しない作品なので、`true` になります |

## パラメータ

| 名前 | 概要 | 使用例 |
| --- | --- | --- |
| fields | レスポンスボディに含まれるデータのフィールドを絞り込みます。 | fields=id,title |
| filter_ids | 作品を作品IDで絞り込みます。 | filter_ids=1,2,3 |
| filter_season | 作品をリリース時期で絞り込みます。`2016-all` としたときは、2016年にリリースされる作品全てを取得することができます。 | filter_season=2016-spring |
| filter_title | 作品をタイトルで絞り込みます。 | filter_title=shirobako |
| page | ページ数を指定します。 | page=2 |
| per_page | 1ページに何件取得するかを指定します。デフォルトは `25` 件で、`50` 件まで指定できます。 | per_page=30 |
| sort_id | 作品を作品IDで並び替えます。`asc` または `desc` が指定できます。 | sort_id=desc |
| sort_season | 作品をリリース時期で並び替えます。`asc` または `desc` が指定できます。 | sort_season=desc |
| sort_watchers_count | 作品をWatchersの数で並び替えます。`asc` または `desc` が指定できます。 | sort_watchers_count=desc |

## リクエスト例

```
$ curl -X GET https://api.annict.com/v1/works?access_token=(access_token)
```

```json
{
  "works": [
    {
      "id": 4168,
      "title": "SHIROBAKO",
      "title_kana": "しろばこ",
      "media": "tv",
      "media_text": "TV",
      "season_name": "2014-autumn",
      "season_name_text": "2014年秋",
      "released_on": "2014-10-09",
      "released_on_about": "",
      "official_site_url": "http://shirobako-anime.com",
      "wikipedia_url": "http://ja.wikipedia.org/wiki/SHIROBAKO",
      "twitter_username": "shirobako_anime",
      "twitter_hashtag": "musani",
      "mal_anime_id": "25835",
      "images": {
        "recommended_url": "http://shirobako-anime.com/images/ogp.jpg",
        "facebook": {
          "og_image_url": "http://shirobako-anime.com/images/ogp.jpg"
        },
        "twitter": {
          "mini_avatar_url": "https://twitter.com/shirobako_anime/profile_image?size=mini",
          "normal_avatar_url": "https://twitter.com/shirobako_anime/profile_image?size=normal",
          "bigger_avatar_url": "https://twitter.com/shirobako_anime/profile_image?size=bigger",
          "original_avatar_url": "https://twitter.com/shirobako_anime/profile_image?size=original",
          "image_url": ""
        }
      },
      "episodes_count": 24,
      "watchers_count": 1254
    },
  ]
...
```
