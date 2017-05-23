# Query

## Connections

### searchWorks: [WorkConnection](objects/work-connection.md)

各種条件に該当する作品を返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| first | [Int](scalars/int.md) | 最初のn件取得する |
| after | [String](scalars/string.md) | 指定したIDより後の要素を取得する |
| last | [Int](scalars/int.md) | 最後のn件取得する |
| before | [String](scalars/string.md) | 指定したIDより前の要素を取得する |
| annictIds | [[Int](scalars/int.md)!] | 取得したい作品のAnnict ID |
| seasons | [String](scalars/string.md)! | 取得したい作品のシーズン (`2017-spring` など) |
| titles | [String](scalars/string.md)! | 取得したい作品のタイトル |
| orderBy | [WorkOrder](input-objects/work-order.md) | 並び順 |


## Fields

### node: [Node](interfaces/node.md)

指定したIDでオブジェクトを1つ返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| id | [ID](scalars/id.md)! | オブジェクトのID |


### nodes: [[Node](interfaces/node.md)]!

指定した複数のIDでオブジェクトを返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| ids | [[ID](scalars/id.md)!]! | オブジェクトのID |


### user: [User](objects/user.md)

指定した `username` でオブジェクトを1つ返します。

| 引数 | 型 | 概要 |
| --- | --- | --- |
| username | [String](scalars/string.md)! | ユーザ名 |


### viewer: [User](objects/user.md)

アクセストークンを生成したユーザ (APIを利用している本人) を返します。
