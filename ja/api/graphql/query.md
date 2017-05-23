# Query

## Connections

### searchWorks: [WorkConnection](/api/graphql/objects/work-connection.md)

各種条件に該当する作品を返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| first | [Int](/api/graphql/scalars/int.md) | 最初のn件取得する |
| after | [String](/api/graphql/scalars/string.md) | 指定したIDより後の要素を取得する |
| last | [Int](/api/graphql/scalars/int.md) | 最後のn件取得する |
| before | [String](/api/graphql/scalars/string.md) | 指定したIDより前の要素を取得する |
| annictIds | [[Int!]](/api/graphql/scalars/int.md) | 取得したい作品のAnnict ID |
| seasons | [String!](/api/graphql/scalars/string.md) | 取得したい作品のシーズン (`2017-spring` など) |
| titles | [String!](/api/graphql/scalars/string.md) | 取得したい作品のタイトル |
| orderBy | [WorkOrder](/api/graphql/input-objects/work-order.md) | 並び順 |


## Fields

### node: [Node](/api/graphql/interfaces/node.md)

指定したIDでオブジェクトを1つ返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| id | [ID!](/api/graphql/scalars/id.md) | オブジェクトのID |


### nodes: [[Node]](/api/graphql/interfaces/node.md)!

指定した複数のIDでオブジェクトを返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| ids | [[ID!]!](/api/graphql/scalars/id.md) | オブジェクトのID |


### user: [User](/api/graphql/objects/user.md)

指定した `username` でオブジェクトを1つ返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| username | [String!](/api/graphql/scalars/string.md) | ユーザ名 |


### viewer: [User](/api/graphql/objects/user.md)

アクセストークンを生成したユーザ (APIを利用している本人) を返します。
