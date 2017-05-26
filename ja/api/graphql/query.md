# Query

## Connections

#### searchWorks: [WorkConnection](/api/graphql/objects/work-connection.md)

各種条件に該当する作品を返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| first | [Int](/api/graphql/scalars/int.md) | 最初のn件取得する |
| after | [String](/api/graphql/scalars/string.md) | 指定したIDより後の要素を取得する |
| last | [Int](/api/graphql/scalars/int.md) | 最後のn件取得する |
| before | [String](/api/graphql/scalars/string.md) | 指定したIDより前の要素を取得する |
| annictIds | [[Int](/api/graphql/scalars/int.md)!] | 取得したい作品のAnnict ID |
| seasons | [String](/api/graphql/scalars/string.md)! | 取得したい作品のシーズン (`2017-spring` など) |
| titles | [String](/api/graphql/scalars/string.md)! | 取得したい作品のタイトル |
| orderBy | [WorkOrder](/api/graphql/input-objects/work-order.md) | 並び順 |


##### 例

クエリ:

```
query {
  searchWorks(seasons: ["2017-spring"], orderBy: { field: WATCHERS_COUNT, direction: DESC }, first: 5) {
    edges {
      node {
        id
        annictId
        title
        media
        watchersCount
      }
    }
  }
}
```

結果:

```json
{
  "data": {
    "searchWorks": {
      "edges": [
        {
          "node": {
            "id": "V29yay00NzE0",
            "annictId": 4714,
            "title": "エロマンガ先生",
            "media": "TV",
            "watchersCount": 705
          }
        },
        {
          "node": {
            "id": "V29yay00OTI0",
            "annictId": 4924,
            "title": "進撃の巨人 Season 2",
            "media": "TV",
            "watchersCount": 647
          }
        },
        {
          "node": {
            "id": "V29yay01MDYy",
            "annictId": 5062,
            "title": "サクラクエスト",
            "media": "TV",
            "watchersCount": 608
          }
        },
        {
          "node": {
            "id": "V29yay00NzI1",
            "annictId": 4725,
            "title": "冴えない彼女の育てかた♭",
            "media": "TV",
            "watchersCount": 557
          }
        },
        {
          "node": {
            "id": "V29yay01MDc4",
            "annictId": 5078,
            "title": "終末なにしてますか？ 忙しいですか？ 救ってもらっていいですか？",
            "media": "TV",
            "watchersCount": 453
          }
        }
      ]
    }
  }
}
```


## Fields

#### node: [Node](/api/graphql/interfaces/node.md)

指定したIDでオブジェクトを1つ返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| id | [ID](/api/graphql/scalars/id.md)! | オブジェクトのID |


##### 例

クエリ:

```
query {
  node(id: "V29yay00NzE0") {
    ... on Work {
      title
    }
  }
}
```

結果:

```json
{
  "data": {
    "node": {
      "title": "エロマンガ先生"
    }
  }
}
```


#### nodes: [[Node](/api/graphql/interfaces/node.md)]!

指定した複数のIDでオブジェクトを返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| ids | [[ID](/api/graphql/scalars/id.md)!]! | オブジェクトのID |


##### 例

クエリ:

```
query {
  nodes(ids: ["V29yay00NzE0", "V29yay01MDYy"]) {
    ... on Work {
      title
    }
  }
}
```

結果:

```json
{
  "data": {
    "nodes": [
      {
        "title": "エロマンガ先生"
      },
      {
        "title": "サクラクエスト"
      }
    ]
  }
}
```


#### user: [User](/api/graphql/objects/user.md)

指定した `username` でオブジェクトを1つ返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| username | [String](/api/graphql/scalars/string.md)! | ユーザ名 |


##### 例

クエリ:

```
query {
  user(username: "shimbaco") {
    name
  }
}
```

結果:

```json
{
  "data": {
    "user": {
      "name": "Koji Shimba"
    }
  }
}
```


#### viewer: [User](/api/graphql/objects/user.md)

アクセストークンを生成したユーザ (APIを利用している本人) を返します。


##### 例

クエリ:

```
query {
  viewer {
    username
    name
  }
}
```

結果:

```json
{
  "data": {
    "viewer": {
      "username": "shimbaco",
      "name": "Koji Shimba"
    }
  }
}
```
