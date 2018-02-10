# Episode

## Implements

- [Node](/api/graphql/interfaces/node.md)


## Fields

#### annictId: [Int](/api/graphql/scalars/int.md)!

#### id: [ID](/api/graphql/scalars/id.md)!

#### nextEpisode: [String](/api/graphql/objects/episode.md)

#### number: [Int](/api/graphql/scalars/int.md)

#### numberText: [String](/api/graphql/scalars/string.md)

#### prevEpisode: [String](/api/graphql/objects/episode.md)

#### recordCommentsCount: [Int](/api/graphql/scalars/int.md)!

#### records: [RecordConnection](/api/graphql/objects/record-connection.md)

| 引数 | 型 | 概要 |
| --- | --- | --- |
| first | [Int](/api/graphql/scalars/int.md) | 最初のn件取得する |
| after | [String](/api/graphql/scalars/string.md) | 指定したIDより後の要素を取得する |
| last | [Int](/api/graphql/scalars/int.md) | 最後のn件取得する |
| before | [String](/api/graphql/scalars/string.md) | 指定したIDより前の要素を取得する |
| orderBy | [RecordOrder](/api/graphql/input-objects/record-order.md) | 並び順 |
| hasComment | [String](/api/graphql/scalars/boolean.md) | 感想付きの記録だけに絞り込むかどうか |

#### recordsCount: [Int](/api/graphql/scalars/int.md)!

#### sortNumber: [Int](/api/graphql/scalars/int.md)!

#### title: [String](/api/graphql/scalars/string.md)

#### viewerDidTrack: [Boolean](/api/graphql/scalars/boolean.md)!

#### viewerRecordsCount: [Int](/api/graphql/scalars/int.md)!

#### work: [Work](/api/graphql/objects/work.md)!
