EliteMobsが持つWorldGuardフラグとその機能は以下の通りです。

***

# elitemob-spawning (allow/deny)
このフラグは、その地域でElite Mobがスポーンできるかどうかを設定します。デフォルトでは、Elite Mobはどこでもスポーンできるようになっているため、このフラグの主な用途は特定の地域でそれらを無効にすることです。ワールド全体でElite Mobのスポーンを無効にしたい場合は、代わりにValidWorlds.ymlファイルを編集することをお勧めします。

***

# elitemob-only-spawning (allow/deny)
このフラグは、特定の地域でElite Mobのみがスポーンできるようにするかどうかを設定します。これにより、その地域でスポーンするElite Mobの量が増加するわけではなく、Elite Mobではないエンティティがその地域でスポーンするのを防ぐだけです。これは、アリーナや高難易度ゾーンなど、Elite Mobのみがスポーンできるエリアを設けたいユーザー向けです。

***

# elitemobs-antiexploit (allow/deny)
このフラグは、特定の地域でアンチエクスプロイトがトリガーできるかどうかを設定します。Allowにするとアンチエクスプロイトが実行され、denyにすると実行されません。あらかじめエクスプロイトがないことをテスト済みの既製アリーナやダンジョンでは、Denyにすることをお勧めします。

***

また、注意点として、NPCはWorldGuardとのサードパーティ互換性の一環として、mob-spawning denyフラグを上書きします。特定のエリアにNPCを配置したくない場合は、手動で削除することをお勧めします。

***

# elitemobs-maximum-level
特定の地域でスポーンできるElite Mobの最大レベルを設定します。自然スポーンするエリートのみに影響します（カスタムボスはこの影響を受けません）。レベルは整数値でなければなりません（`1.5`のような値は使用できません。`1`や`2`のような整数を使用する必要があります）。

***

# elitemobs-minimum-level
特定の地域でスポーンできるElite Mobの最小レベルを設定します。自然スポーンするエリートのみに影響します（カスタムボスはこの影響を受けません）。レベルは整数値でなければなりません（`1.5`のような値は使用できません。`1`や`2`のような整数を使用する必要があります）。

***

# elitemobs-dungeon
CUSTOMスポーン理由でスポーンする通常のMob、リージョナルボス、カスタムボスのみをそのエリアで許可するように設定します。これはミニダンジョンで使用するためのものです。
