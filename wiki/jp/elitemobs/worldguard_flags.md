```markdown
# WorldGuard フラグ

ここに、EliteMobs が持つ WorldGuard フラグとその機能をリストします。


***

# elitemob-spawning (許可/拒否)
リージョンにエリートモブをスポーンさせるかどうかを設定します。デフォルトの動作では、エリートモブはすべての場所にスポーンすることを許可されているため、このフラグは、特定のリージョンでエリートモブを無効にするために使用されます。ワールド全体でエリートモブのスポーンを無効にする場合は、`ValidWorlds.yml` ファイルを編集することをお勧めします。


***

# elitemob-only-spawning (許可/拒否)
リージョンにエリートモブのみをスポーンさせるかどうかを設定します。これにより、エリアにスポーンするエリートモブの数は増えません。これは、アリーナや難易度が高いゾーンなど、エリートモブのみがスポーンするエリアを設けたいユーザー向けです。


***

# elitemobs-antiexploit (許可/拒否)
リージョンでアンチエクスプロイトをトリガーできるかどうかを設定します。許可するとアンチエクスプロイトが実行され、拒否すると実行されなくなります。事前にテスト済みのアリーナやダンジョンの場合、拒否することをお勧めします。

***

また、注意してください。NPC は、WorldGuard とのサードパーティ互換性のために、モブのスポーン拒否フラグを上書きします。エリアに NPC を配置したくない場合は、手動で削除することをお勧めします。

***

# elitemobs-maximum-level

リージョンにスポーンできるエリートモブの最大レベルを設定します。自然発生したエリートにのみ影響します（カスタムボスは無視されます）。レベルは整数値である必要があります（`1.5` などの値は使用できません。`1` や `2` などの整数を使用する必要があります）。

***

# elitemobs-minimum-level

リージョンにスポーンできるエリートモブの最小レベルを設定します。自然発生したエリートにのみ影響します（カスタムボスは無視されます）。レベルは整数値である必要があります（`1.5` などの値は使用できません。`1` や `2` などの整数を使用する必要があります）。

***

# elitemobs-dungeon

エリアを、カスタムのスポーン理由でスポーンされた通常のモブ、リージョンボス、カスタムボスのみに限定します。これは、ミニダンジョンで使用します。

```



