```markdown
[![webapp_banner.jpg](../../../img/wiki/webapp_banner.jpg)](https://magmaguy.com/webapp/webapp.html)

# ワールドボスの作成
*ワールドボスは、リージョンボスと呼ばれることもあります。*

## ワールドボスとは？

ワールドボスは、特定の場所に特定の時間間隔でスポーンするように設定されたカスタムボスです。これは、ダンジョンで使用されるボスでもあります。ただし、このセクションでは、ダンジョン外で使用されるワールドボスの作成について説明します。

## ワールドボスは何のためにあるのか？

ワールドボスは、プレイヤーが固定されたチャレンジに立ち向かうことができ、同時に報酬が得られることを保証します。

## ワールドボスを作成するために必要なもの

1. **場所**. ワールドガードのリージョンで領域を保護し（プレイヤーが罠を仕掛けられないように）、地形を戦闘で悪用できないようにする必要があります（プレイヤーがトラップを仕掛けられないように）。ボス部屋があるのが理想ですが、Minecraft の攻撃範囲の関係で、およそ 15 ブロックの半径（30 ブロックの幅）を確保してください。
2. **リスポーン時間**. リスポーンタイマーは不可欠です。30 分未満のリスポーンタイマーは避けるべきです。そうしないと、ボスのリスポーンがイベントとして感じられなくなります。1 時間は適切な時間ですが、ボスを 1 日に 1 回、または週に 1 回だけリスポーンさせることも考えられます。
3. **脱出時間**. リスポーン時間が長いほど、脱出時間も長くする必要があります。また、脱出時間は、プレイヤーがボスに快適に挑めるだけの長さにする必要があります。脱出タイマーは、プレイヤーがボスを意図的に倒すことを許可したくない場合に重要です。これは、週単位でリスポーンする巨大なボスを作成する場合には、必須ではありませんし、推奨されません。
4. **カスタムボス**. ワールドボスは、実際にはスポーンルールがカスタマイズされたカスタムボスです。レイドサイズの戦闘に適したパワーを選択してください。
5. **魅力的なloot**. ワールドボスの大きな魅力は、チャレンジのほかにlootです。プレイヤーが他の場所では入手できないものを手に入れることができるようにしてください。
6. **テーマ**. 良いリージョンボスには、テーマ、テーマに合わせた場所、テーマに合わせたlootが必要です。

## ワールドボス用のカスタムボスの設定オプション:

これらの設定は、通常の カスタムボスの設定ファイルに追加されます。[詳細な wiki ページはこちらをご覧ください。]($language$/elitemobs/creating_bosses.md).

<div align="center">

***

### isRegionalBoss

ボスがリージョンボスかどうかを設定します。リージョンボスはワールドボスとも呼ばれるため、`true` に設定する必要があります。

| キー       |       値        | デフォルト |
|-----------|:-------------------:|:-------:|
| `isRegionalBoss` | [Boolean](#boolean) | `false` |

<details> 

<summary><b>例</b></summary>

<div align="left">

```yml
isRegionalBoss: true
```

</div>

</details>

***

### spawnLocations

スポーン位置は、ゲーム内から `/em addSpawnLocation <filename.yml>` コマンドを使用して設定する必要があります。

設定から手動で位置を追加することはできますが、間違えやすいので、お勧めしません。

| キー              |           値            | デフォルト |
|------------------|:---------------------------:|:-------:|
| `spawnLocations` | [String List](#string_list) |  none   |

<details> 

<summary><b>例</b></summary>

<div align="left">

設定ファイル内の位置（上級者向け） リージョンボスの設定ファイルは、複数のスポーン位置とリスポーンタイマーを保存することで、そのリージョンボスのすべてのインスタンスを 1 つのファイルに保存します。

実際には、このエントリは次のようになります。

```yaml
spawnLocations:
- elitemobs_sewer_maze,-70.17178578884845,168.2,-173.17112099568718,-271.24023,64.19999:1610710903931
- elitemobs_sewer_maze,-135.02262355317436,168.2,-153.28849346821508,-98.53906,60.750263:1609026066482
- elitemobs_sewer_maze,-70.43846307626053,168.2,-174.13499832314378,-271.24023,64.19999:1610710886530
- elitemobs_sewer_maze,-130.39762674971664,168.2,-171.67396911490718,-47.532227,51.900173:1609026066482
- elitemobs_sewer_maze,-117.12782160766056,162.2,-166.40989416757444,-71.37402,-1.4997427:1610710974882
- elitemobs_sewer_maze,-105.13138759611667,168.2,-169.85898023126538,-124.34766,41.24988:1610710945331
- elitemobs_sewer_maze,-106.21847515732084,169.2,-152.3609257554766,-170.86523,21.450315:1610537606222
```

には、7 つの異なるリージョンボスが、異なる場所に、異なるリスポーンタイマーで含まれています。

詳細を分解してみましょう。最初のリージョンボスを見てみましょう。

```yaml
- elitemobs_sewer_maze,-70.17178578884845,168.2,-173.17112099568718,-271.24023,64.19999:1610710903931
```

これは、`world,x,y,z,pitch,yaw:unixTimeStamp` の形式に従っているため、ボスは `elitemobs_sewer_maze` というワールドに、x = `-70.17178578884845`、y = `168.2`、z = `-173.17112099568718`、pitch = `-271.24023`、yaw = `64.19999` でスポーンします。

Unix タイムスタンプは、ボスがリスポーンする時刻を Unix 時間で保存します。これは、リスポーン時間を再起動を通して保存するために使用されます。この時刻に対応する時間を確認したい場合は、オンラインで無数の Unix 時間から実時間への変換ツールを見つけることができます。

特定のボスをリロードまたは再起動後にリスポーンさせたい場合は、`：unixTimeStamp` エントリを削除するだけです。

</div>

</details>

***

### spawnCooldown

ボスがリスポーンするまでの時間（分）を設定します。

**注意：大きなボスの場合は、長いリスポーン時間をお勧めします！**。

| キー       |       値        | デフォルト |
|-----------|:-------------------:|:-------:|
| `spawnCooldown` | [Integer](#integer) |  none   |

<details> 

<summary><b>例</b></summary>

<div align="left">

```yml
spawnCooldown: 20
```

</div>

</details>

***

### leashRadius

ワールドボスがスポーンポイントから移動できる距離を設定します。この距離を超えると、スポーンポイントにテレポートされます。これにより、プレイヤーがボスを戦いやすくするために、ボスを他の場所に移動することを防ぎます。

**注意: リーシュを 20 ブロックよりも短くする必要がある戦闘エリアは避けるようにしてください。そうしないと、戦闘が難しくなります。**

| キー       |       値        | デフォルト |
|-----------|:-------------------:|:-------:|
| `leashRadius` | [Integer](#integer) |  none   |

<details> 

<summary><b>例</b></summary>

<div align="left">

```yml
leashRadius: 30
```

</div>

</details>

***

### Transitive Blocks

`onSpawnBlockStates` と `onRemoveBlockStates` とも呼ばれます。

これらの値により、リージョンボスは、戦闘状態になるとブロックをスポーンさせ、削除されるとブロックを削除することができます。つまり、タイムアウトによって脱出する場合も、死亡する場合も、ブロックを削除することができます。

**これは、フェーズボスと一緒に使用する場合、戦闘中にドアやエリアを開閉したり、アリーナを変更したりするために使用できる方法です！**

| キー       |          値          | デフォルト |
|-----------|:------------------------:|:-------:|
| `onSpawnBlockStates` | 詳細な説明を参照 |  none   |


| キー       | Values  | デフォルト |
|-----------|:-------:|:-------:|
| `onRemoveBlockStates` | 詳細な説明を参照 |  none   |

<details> 

<summary><b>詳細な説明</b></summary>

<div align="left">

**すべてのブロックはスポーン位置を基準としています。ブロックの設定を開始する前に、最終的なスポーン位置を確認してください。**

</br>すでに大きな Transitive Block 領域を作成し、ボスを移動する必要があるが、Transitive Block をやり直したくない場合は、EliteScript の [Teleport]($language$/elitemobs/elitescript_actions.md&section=teleport) アクションを使用して、ボスをスポーン後に正しい場所に移動させることができます。ただし、リーシュも調整する必要があることに注意してください。

ブロックの設定は複雑なため、手動で行うことはお勧めしません。次のコマンドを使用して設定してください。

- /em registerblocks <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em registerblocksedit <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em registerblocksarea <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em registerblocksareaedit <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em cancelblocks

分解してみましょう。

**/em registerblocks <regional\_boss\_file.yml> <on\_spawn/on\_remove>**

最も基本的なコマンドです。これは、1 回実行するとオンになり、もう一度実行するとコミットされるトグルです。他のすべてのコマンドと同様に、`on_spawn` 状態または `on_remove` 状態のいずれかのために、これらのブロックを変更するように設定します。

`on_spawn` を登録する場合、これはボスがスポーンしたとき、またはリスポーンしたときにブロックを変更します。`on_remove` を登録する場合、これはボスが死亡したとき、またはカスタムボスのタイムアウトメカニズムを使用してタイムアウトしたときにブロックを変更します。

ブロックを登録するには、この設定がオンになっている間に、変更したいブロックを配置または削除するだけです。

**/em registerblocksedit <regional\_boss\_file.yml> <on\_spawn/on\_remove>**

すでに設定されているブロックを変更する場合は、このコマンドを使用できます。`/em registerblocks <regional_boss_file.yml> <on_spawn/on_remove>` と非常によく似た方法で動作します。

**/em registerblocksarea <regional\_boss\_file.yml> <on\_spawn/on\_remove>**

`/em registerblocks <regional_boss_file.yml> <on_spawn/on_remove>` と同様に、これによりブロックを登録できますが、個別にブロックを選択するのではなく、2 つの対角線上にあるコーナー（ワールドエディタ/ワールドガードのリージョンの選択と同じ）を選択することで、ブロックを選択できます。 

安全上の理由から、リージョンの選択には、200 ブロックの制限があります（デフォルトでは、config.yml で変更可能です）。すべてのブロックが同じ tick で変更されるため、多くの地形を変更する場合、これらの変更を実行すると、大きなラグが発生する可能性があります。

**/em registerblocksareaedit <regional_boss_file.yml> <on_spawn/on_remove>**

`/em registerblocksedit` と同じように動作しますが、エリア用です。これは、エリアの登録ブロック数の上限（デフォルトは 200）を超えるために使用できます。

**/em cancelblocks**

ブロックを登録しているときに誤って操作した場合、いつでもこのコマンドを実行して登録をキャンセルできます。これにより、その編集/登録で開始した変更が元に戻されます。

</div>

</details>

</div>

***

### alert

<div align="center">

ボスが警戒しているかどうかを設定します。デフォルトでは、リージョンボスは、戦闘状態ではないときに、速度が遅くなり、攻撃対象を認識する距離が短くなります。この設定により、リージョンボスは、戦闘状態ではない場合でも、速度が遅くなったり、攻撃対象を認識する距離が短くなったりすることを防ぐため、戦闘状態内でも外でも常に同じように動作します。

</div>

| キー | 値 | デフォルト |
|-|:-:|-|
| `alert` | [Boolean](#boolean) | `true` |

<details>

<summary><b>例</b></summary>

<div align="left">

```yml
alert: true
```

</div>

</details>

***

### removeAfterDeath

<div align="center">

リージョンボスを倒した後、リージョンボスを永続的に削除するかどうかを設定します。これは、BetterStructures の神殿で使用される方法で、リージョンボスは 1 回だけ戦って、その場所では二度と戦わないように設計されています。

</div>

| キー | 値 | デフォルト |
|-|:-:|-|
| `removeAfterDeath` | [Boolean](#boolean) | `false` |

<details>

<summary><b>例</b></summary>

<div align="left">

```yml
removeAfterDeath: true
```

</div>

</details>

***

## インスタンスボス

<div align="center">

インスタンスボスは、インスタンスダンジョンで使用されるリージョンボスのサブタイプです。

| キー | 説明 | 値 | デフォルト |
|-|:-:|:-|-|
| `instanced` | カスタムボスをインスタンス化します。必須 | `true` / `false` | `false` |


インスタンスダンジョンが正常に動作するためには、ボスをインスタンス化する必要があります。また、インスタンスボスでは、リーシュを削除することもお勧めします。

<details> 

<summary><b>例</b></summary>

<div align="left">

```yml
instanced: true
```

</div>

</details>

</div>

```

