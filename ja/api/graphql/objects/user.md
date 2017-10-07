# User

## Implements

- [Node](/api/graphql/interfaces/node.md)


## Fields

#### activities: [ActivityConnection](/api/graphql/objects/activity-connection.md)

| 引数 | 型 | 概要 |
| --- | --- | --- |
| first | [Int](/api/graphql/scalars/int.md) | 最初のn件取得する |
| after | [String](/api/graphql/scalars/string.md) | 指定したIDより後の要素を取得する |
| last | [Int](/api/graphql/scalars/int.md) | 最後のn件取得する |
| before | [String](/api/graphql/scalars/string.md) | 指定したIDより前の要素を取得する |
| orderBy | [ActivityOrder](/api/graphql/input-objects/activity-order.md) | 並び順 |

#### annictId: [Int](/api/graphql/scalars/int.md)!

#### avatarUrl: [String](/api/graphql/scalars/string.md)

#### backgroundImageUrl: [String](/api/graphql/scalars/string.md)

#### createdAt: [DateTime](/api/graphql/scalars/date-time.md)!

#### description: [String](/api/graphql/scalars/string.md)!

#### email: [String](/api/graphql/scalars/string.md)

#### followers: [UserConnection](/api/graphql/objects/user-connection.md)

#### followersCount: [Int](/api/graphql/scalars/int.md)!

#### following: [UserConnection](/api/graphql/objects/user-connection.md)

#### followingActivities: [ActivityConnection](/api/graphql/objects/activity-connection.md)

| 引数 | 型 | 概要 |
| --- | --- | --- |
| first | [Int](/api/graphql/scalars/int.md) | 最初のn件取得する |
| after | [String](/api/graphql/scalars/string.md) | 指定したIDより後の要素を取得する |
| last | [Int](/api/graphql/scalars/int.md) | 最後のn件取得する |
| before | [String](/api/graphql/scalars/string.md) | 指定したIDより前の要素を取得する |
| orderBy | [ActivityOrder](/api/graphql/input-objects/activity-order.md) | 並び順 |

#### followingCount: [Int](/api/graphql/scalars/int.md)!

#### id: [ID](/api/graphql/scalars/id.md)!

#### name: [String](/api/graphql/scalars/string.md)!

#### notificationsCount: [Int](/api/graphql/scalars/int.md)

#### onHoldCount: [Int](/api/graphql/scalars/int.md)!

#### programs: [ProgramConnection](/api/graphql/objects/program-connection.md)

#### recordsCount: [Int](/api/graphql/scalars/int.md)!

#### stopWatchingCount: [Int](/api/graphql/scalars/int.md)!

#### url: [String](/api/graphql/scalars/string.md)

#### username: [String](/api/graphql/scalars/string.md)!

#### viewerCanFollow: [Boolean](/api/graphql/scalars/boolean.md)!

#### viewerIsFollowing: [Boolean](/api/graphql/scalars/boolean.md)!

#### wannaWatchCount: [Int](/api/graphql/scalars/int.md)!

#### watchedCount: [Int](/api/graphql/scalars/int.md)!

#### watchingCount: [Int](/api/graphql/scalars/int.md)!

#### works: [WorkConnection](/api/graphql/objects/work-connection.md)
