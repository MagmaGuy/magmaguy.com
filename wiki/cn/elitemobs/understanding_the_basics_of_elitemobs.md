以下是我尽我所能简要描述的 EliteMobs 的预期游戏循环。本指南旨在帮助想要了解 EliteMobs 功能的新管理员。

# 步骤 1：玩家的初次遭遇

服务器中的玩家将在正常游戏过程中获得盔甲。一旦他们拥有任何铁等级或更好的装备，他们就会开始面对根据玩家所穿盔甲在其周围自然生成的精英怪物。

玩家也可以通过降低他们的[公会等级]($language$/elitemobs/adventurers_guild_world.md)来选择不参与。
<br>这些精英怪物（当它们的等级足够高且未触发反作弊系统时）可以掉落三种类型的战利品：

* 程序生成的战利品（最常见的类型）
* 自定义战利品（有点稀有）
* 精英币

（注意：您可以在[此处]($language$/elitemobs/spawning_tiers_loot.md)阅读有关精英怪物生成和奖励的更多信息）

掠夺后，插件会通知玩家这些硬币可以在[冒险者公会]($language$/elitemobs/adventurers_guild_world.md)的商店中使用和出售物品。

# 步骤 2：发现经济系统

一旦玩家获得了有关出售物品的信息，他们自然会被吸引去出售它们。如果世界设置正确，他们就会找到冒险者公会的 NPC（世界下载和设置的详细信息以及
Spigot 资源帖子）。

他们会发现 EliteMobs 使用自己的货币，这出于平衡原因很有必要。他们还会发现他们可以解锁公会等级，并且稍后会发现，如果他们希望突破
10 级精英怪物，则必须这样做，因为如果不解锁更多等级，他们将无法获得 10 级以上的战利品。

他们还将能够了解任务系统，并开始完成任务以获得额外的货币，这将自然地引导他们去寻找他们原本会避免的对手。他们也可能会找到战斗导师
NPC，他会给他们提供有关战斗系统的提示。总的来说，所有 NPC 都会在玩家与他们互动时给玩家提供重要的建议。

# 步骤 3：进度

现在玩家对他们面前的事情有了一个概念，他们将在通过物品等级升级时与越来越强大的精英怪物战斗。

当他们达到钻石等级时，他们会发现自己被公会等级限制住了，这应该会鼓励他们解锁更高的等级。
<br>
此外，他们还会遇到随机事件，这些事件应该会增加他们对插件提供的各种机制的兴趣，尤其是在[自定义附魔]($language$/elitemobs/custom_enchantments_list.md)
方面，例如火焰喷射器。

# 步骤 4：高等级

一旦玩家升级到大约 80 级的物品等级（或 8 级的公会等级），他们就会开始最大化 EliteMobs
的难度（目前）。高等级战斗需要比低等级更多的策略、计划和战斗执行，因为那时怪物最多有 7 种不同的力量。

他们将能够分辨出他们想要保留哪些战利品以及想要丢弃哪些战利品，并且对他们最喜欢的自定义物品有一个很好的了解。我强烈建议您制作大量的自定义物品，因为这些是目前
EliteMobs 中高层玩家的主要关注点。

# (小型)地下城探索

假设您在某个时候（甚至可能很早就）安装了推荐的[迷你地下城和巢穴]($language$/elitemobs/dungeons.md)，玩家可能会被吸引去挑战巢穴、迷你地下城和冒险。

这些是自定义 Boss 生成的位置，并且在被杀死后会延迟重生，从而创建一个集中的位置，让玩家可以以公平的方式挑战强大的 Boss。

以下是迷你地下城的主要卖点：

* 由于地形是预制的并且受到保护，而且 Boss 也是如此，因此战斗无法被利用。
* 由于它集中了战斗，您可以降低自然怪物的生成率，并最终降低整体性能影响。
* 由于战利品是预制的，因此通常非常特殊，玩家学会去某些地方寻找他们可能喜欢的特定装备。
* 由于 Boss 是预制的，因此战斗是手动平衡的，从而产生更有趣和更具挑战性但公平的战斗。
* 就冒险而言，这些都是完整的巨型冒险地图，其中包含庞大的任务线、支线任务，有时甚至还有竞技场和地下城内的地下城！
* 它看起来很棒，玩家喜欢在其中花费数天的时间。

[有关迷你地下城的更多信息！]($language$/elitemobs/dungeons.md)

# 实例地下城探索

有些地下城是实例挑战。这意味着当一个小组加入地下城时会创建一个世界，并且一旦该小组开始地下城，玩家将无法加入，除非是观看它。
<br>有一个专门的重生系统，在被淘汰之前，玩家每人有 3 次死亡机会。

地下城是 EliteMobs 中最平衡和最发达的内容，因为它们比任何其他内容都更难利用。

地下城有玩家可以选择的难度，而最高的难度是 EliteMobs 中最艰巨的挑战，但也是最有回报的挑战！

[有关地下城的更多信息！]($language$/elitemobs/dungeons.md)

# 竞技场

EliteMobs 还有玩家可以挑战的竞技场。这些是基于波次的挑战，玩家必须克服预设数量的波次。它们会奖励达到特定竞技场波次的玩家。

此内容也是实例化的，并且地下城探索部分的加入和重生限制也适用于此处。

竞技场可能很难击败，因此它们会带来有趣且有益的挑战！
