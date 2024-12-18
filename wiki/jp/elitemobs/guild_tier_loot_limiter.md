# ギルドティア制限

ギルドティアの戦利品制限は、プレイヤーが獲得できる最高の戦利品を、そのプレイヤーのギルドティアに基づいて制限します。

プレイヤーは、冒険者ギルドのハブに行き、ギルド担当のNPCであるジリアンに話しかけるか、*/em rank* コマンドを実行することで、より高いティアをアンロックできます。ランクは、エリートコインで購入することでアンロックされます。

デフォルトでは、プレイヤーは以下のように制限されます（デフォルト設定を使用している場合を想定）。

- ギルドティア1（初期デフォルト）：ティア10までのアイテム、レベル10のモブ
- ギルドティア2：ティア20までのアイテム、レベル20のモブ
- ギルドティア3：ティア30までのアイテム、レベル30のモブ
- ギルドティア4：ティア40までのアイテム、レベル40のモブ
- ギルドティア5：ティア50までのアイテム、レベル50のモブ
- ギルドティア6：ティア60までのアイテム、レベル60のモブ
- ギルドティア7：ティア70までのアイテム、レベル70のモブ
- ギルドティア8：ティア80までのアイテム、レベル80のモブ
- ギルドティア9：ティア90までのアイテム、レベル90のモブ
- ギルドティア10：ティア100までのアイテム、レベル100のモブ

ここからは、ギルドティアをアンロックするためにプレステージレベルが必要になります。

- プレステージ1 ギルドティア11：ティア110までのアイテム、レベル110のモブ
- プレステージ2 ギルドティア12：ティア120までのアイテム、レベル120のモブ
- プレステージ3 ギルドティア13：ティア130までのアイテム、レベル130のモブ
- プレステージ4 ギルドティア14：ティア140までのアイテム、レベル140のモブ
- プレステージ5 ギルドティア15：ティア150までのアイテム、レベル150のモブ
- プレステージ6 ギルドティア16：ティア160までのアイテム、レベル160のモブ
- プレステージ7 ギルドティア17：ティア170までのアイテム、レベル170のモブ
- プレステージ8 ギルドティア18：ティア180までのアイテム、レベル180のモブ
- プレステージ9 ギルドティア19：ティア190までのアイテム、レベル190のモブ
- プレステージ10 ギルドティア20：ティア200までのアイテム、レベル200のモブ

## 仕組みとエッジケース
ギルドティアはプレイヤーが倒せるアイテムのティアを制限するため、これはプレイヤーがスポーンさせることができるモブも一定レベルまでしかできないことを意味します。なぜならモブのレベルはプレイヤーが装備しているギアに基づいているからです。もしプレイヤーがレベルの高い友達と一緒にモブ狩りに行った場合、彼らが手に入れる戦利品は友達よりも低いレベルのものになります。

[ソウルバインド]($language/elitemobs/soulbind.md$)エンチャントと組み合わせることで、パワーレベリングの問題をかなり抑制することができ、管理者は訪問者がサーバーに参加して数分以内に最大ティアに到達したり、新しいプレイヤーがすぐに大量のダイヤモンドティアアイテムを手に入れたりすることを心配する必要がなくなります。さらに、それはプレイヤーに戦利品とのより深い繋がりを与え、戦利品を自分自身だけに属するものとします。
