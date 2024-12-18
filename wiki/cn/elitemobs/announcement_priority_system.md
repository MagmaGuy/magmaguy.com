公告优先级系统管理 EliteMobs 消息的重要性。这些目前仅用于管理自定义首领生成发送的消息。

# 简短的速查表：

* 级别 0：静默 / 对与首领战斗的玩家本地
*   级别 1：聊天消息（如果它有生成消息）
*   级别 2：追踪（如果它有位置消息）
* 级别 3：[Discord 公告（如果它有生成消息并且 DiscordSRV 安装并配置正确）]($language$/elitemobs/discordsrv.md)

# 工作原理：

注意：如果要使用非默认值，则需要使用此优先级系统设置自定义首领。单击[此处]($language$/elitemobs/creating_bosses.md&section=announcementpriority)
了解如何操作。

## 级别 0

强制自定义首领保持静默。这意味着不会发送任何关于它的消息，即使它被配置为具有这些消息，但有一个例外：它们会将死亡消息直接发送给伤害首领的玩家。

## 级别 1

**这是默认设置。** 如果配置为这样做，自定义首领将能够在聊天中发送消息。如果它们被配置为具有这些消息，它们将发送生成、死亡和逃脱消息。

## 级别 2

自定义首领将具有与级别 1 中相同的行为，并且如果它有与其关联的位置消息，还可以在生成时被玩家跟踪。玩家可以单击聊天来在生成时跟踪它，或者可以使用
/em 菜单来跟踪它。

## 级别 3

自定义首领具有与级别 2 中相同的行为，并且还会将消息发送到配置为发送有关 EliteMobs 通知的 Discord
房间。[有关如何设置此功能的页面可以在此处找到。]($language$/elitemobs/discordsrv.md) Discord 上的消息将与聊天消息相同 -
生成/死亡/逃脱
