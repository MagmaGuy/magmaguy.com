# 既存のミニダンジョンの変更

多くの要望に応え、このページでは既存のミニダンジョンを変更する基本について説明します。これはステップバイステップのガイドではなく、システムの変更方法を広く概観するものです。これらの値を変更するには、[カスタムボス]($language$/elitemobs/creating_bosses.md)
と[カスタムアイテム]($language$/elitemobs/creating_items.md)に関するWikiページを読む必要があります。

### ダンジョンの難易度変更

ダンジョンの難易度を変更したい理由は3つあります。以下に説明します。

### ボスのダメージ/体力倍率の変更

これは最も簡単な変更です。ボスが与えるダメージが少なすぎたり多すぎたり、体力が少なすぎたり多すぎたりする場合は、`custombosses`
フォルダーにあるボスファイル内のこれらの修飾子に関連付けられた値を変更できます。

変更する値の例：
```yml
healthMultiplier: 0.5
damageMultiplier: 0.5
```

ボスのステータスの詳細はこちら[here]($language$/elitemobs/creating_bosses.md&section=healthmultiplier)。

多くのパワーの場合、ダメージ倍率はパワーによって適用されるダメージを変更しないことに注意してください。パワーを変更する方法については、次のセクションを参照してください。

### ボスのパワーの変更

EliteMobsの主な難しさは、ボスが持つさまざまなパワーに対処することです。レベルの高いボスはより多くの、より難しいパワーを持つ傾向があり、レベルの低いボスはより少なく、より簡単なパワーを持つ傾向があります。同じボスで一緒に使用される特定のパワーは戦闘を容易にし、一緒に配置された他のパワーは戦闘を大幅に難しくする可能性があります。

変更する値の例：
```yml
powers:
- invulnerability_fire.yml
- invulnerability_arrow.yml
```

ボスのパワーの詳細はこちら[here]($language$/elitemobs/creating_bosses.md&section=powers)。

ここにリストするにはパワーの組み合わせが多すぎるため、パワーがどのように機能するかを学び、あまり難しくも簡単でもないと思われるエンカウンターのスイートスポットを見つけるために、エンカウンターをプレイテストする必要があります。

### ボスのレベル変更

これは最も頻繁に質問される質問であり、可能ではありますが、ボスを適切にスケールアップまたはスケールダウンするために、いくつかの手順が必要です。

変更する値の例：
```yml
level: 21
```

ボスのレベルの詳細はこちら[here]($language$/elitemobs/creating_bosses.md&section=level)。

これは、ダメージ/体力倍率に関して述べたことの両方の組み合わせです。レベルの低い/高いボスは、戦闘を適切に感じさせるために、わずかに異なる体力とダメージの倍率が必要になる場合があります。

ただし、ここで考慮すべき最も重要な側面は、ボスのパワーです。レベルの低いボスとレベルの高いボスは、戦闘がどれほど難しいことを目的としているかによって、かなり異なるパワーセットを持つ傾向があります。レベル10のボスとレベル200のボスで同じパワーセットを持つと、通常、難易度が大きく異なるように感じられる戦闘になります。繰り返しますが、スイートスポットを見つける唯一の方法は、プラグインのパワーがどのように機能するかを学び、プレイテストすることです。

そして、最後になりましたが、**最も重要なことです！**
カスタムルートを微調整することをお勧めします。EliteMobsのほとんどのボスはカスタムルートを持っており、ボスのレベルを切り替えている場合は、ドロップするルートの性質を変更することをお勧めします。

変更する値の例：
```yml
uniqueLootList:
  - filename: mob_drop_boots.yml
    chance: 0.05
```

ルートドロップの詳細はこちら[here]($language$/elitemobs/loot_tables.md)。

### 変更したコンテンツのクレジット/公開

EliteMobsでは、作成したダンジョンを適切なチャンネル（Discord）に自由に投稿できます。ただし、作成したものが既存のダンジョンの変更にすぎない場合、特にそれが小さな調整のみである場合、またはプレミアムコンテンツを含んでいる場合、または派生したものである場合は、送信が削除される可能性があります（明らかな理由で）。

購入またはダウンロードしたコンテンツは、ご自身のネットワーク内での使用のためにサーバーのニーズに合わせて調整するために、自由に変更できますが、明らかな理由から、これは再配布権を提供するものではありません。

コミュニティの送信物は、理由を問わず、いつでも削除する権利を留保しますが、実際にそうしなければならないのは嫌です。

### 詳細情報

このページをさらに拡張する必要があると思われる場合は、Discordに何を追加する必要があるかを提案してください。ここに記載されているさまざまなシステムに関する詳細情報は、他のWikiページに記載されています。
