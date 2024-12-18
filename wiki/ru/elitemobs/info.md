Добро пожаловать в вики EliteMobs!

# Лицензия

Исходный код EliteMobs распространяется под лицензией [GPLV3](https://choosealicense.com/licenses/gpl-3.0/), а эта вики предоставляется под лицензией [CC0](https://choosealicense.com/licenses/cc0-1.0/).

Не стесняйтесь распространять и изменять информацию в этой вики.

# Версии

Начиная с версии 9.0.0 EliteMobs, единственная поддерживаемая версия Minecraft - 1.21 и выше.

Для тех, кто ищет совместимость со старыми версиями Minecraft (1.19.4 - 1.20.4), пожалуйста, используйте версию 8 EliteMobs.

**Примечание: Никакая версия EliteMobs не поддерживает версии Minecraft 1.20.5 и 1.20.6.**

# Для чего нужен EliteMobs?

EliteMobs стремится расширить эндгейм Minecraft, внедряя различный контент, связанный с боссами.

Это означает:
- Динамические боссы (мобы с уровнями)
- Пользовательские боссы
- События
- Арены
- Мировые подземелья
- Инстансные подземелья
- Случайные подземелья в открытом мире (с интеграцией BetterStructures)
- Пользовательские предметы (элитные предметы/лут)
- ... и многое другое!

Плагин не нацелен на замену ванильного контента Minecraft, а скорее на его дополнение, позволяя игрокам при желании отказаться от контента EliteMobs. Предметы EliteMobs обычно не влияют на PvP или ванильный бой Minecraft, поскольку их бонусы к урону и защите применяются только во время боя с EliteMobs.

# Обзор возможностей EliteMobs

В этом разделе мы рассмотрим некоторые из **основных** функций, которые предлагает EliteMobs, что они собой представляют и как их можно отключить. Полный список функций смотрите [на этой странице]($language$/elitemobs/feature_list.md&section=feature-list).

Вы также можете ознакомиться с [этой]($language$/elitemobs/understanding_the_basics_of_elitemobs.md) страницей, чтобы узнать, как игроки должны взаимодействовать с EliteMobs.

## Динамические боссы

Динамические боссы - одна из основных особенностей EliteMobs. Он заменяет определенный процент ванильных спавнов на спавны элитных мобов.

Элиты - это более сильные мобы, созданные для того, чтобы бросить вызов игрокам и вознаградить их возможным выпадением лута после поражения. Уровень элит определяется качеством брони и снаряжения, экипированного игроком. Обычное снаряжение Minecraft имеет уровень, определяемый качеством материала, как объяснено [здесь]($language$/elitemobs/spawning_tiers_loot.md&section=material-levels). Однако, по мере того как игроки побеждают элит и получают лучший лут, они в конечном итоге начнут получать элитные предметы с установленными уровнями, что упростит прогнозирование уровней элит, которые будут появляться.

Это означает, что уровни игроков определяются экипировкой, которую они носят, а уровни элит определяются уровнями игроков.
В EliteMobs нет системы опыта, все развитие уровня игрока зависит от экипировки.

Вы можете настроить сложность элит, изменив значения `damageToEliteMobMultiplierV2` и `damageToPlayerMultiplierV2` в *MobCombatSettings.yml*. Подробнее об этом можно узнать [здесь]($language$/elitemobs/elitemobs_config_settings.md&section=mobcombatsettings.yml).

Если вы хотите полностью отключить эту функцию, вы можете сделать это, установив значение `doNaturalEliteMobSpawning` на `false`.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_dynamic_boss.jpg](../../../img/wiki/eminfo_dynamic_boss.jpg)

</details>

</div>

## Элитные предметы/Лут

В EliteMobs есть случайно сгенерированные предметы, которые можно найти в магазинах или получить от элит. Также есть пользовательские предметы, которые обычно встречаются в подземельях и другом элитном контенте.

Элитные предметы похожи на ванильные предметы, за исключением того, что они обычно оснащены дополнительными "плюшками" и более мощные, чем все, что вы можете найти в ванильном Minecraft. Некоторые элитные предметы будут иметь характеристики, которые называются **Элитная острота** и **Элитная защита**, эти характеристики будут применяться только тогда, когда игроки сражаются с элитами, и не влияют на ванильных мобов.

Элитные предметы также могут иметь чары, [Пользовательские чары]($language$/elitemobs/custom_enchantments_list.md) и эффекты зелий.

Вы можете отключить элитные предметы, открыв *ItemSettings.yml* и установив значение `doEliteMobsLoot` на `false`. (Не рекомендуется, делает прогрессию уровня MMORPG невозможной.)

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_elite_items.jpg](../../../img/wiki/eminfo_elite_items.jpg)

</details>

</div>

## События

События - это уникальные встречи в EliteMobs, которые могут запускаться случайным образом на основе таймера или определенных действий игрока, таких как добыча блока или рубка дерева.

В этих встречах участвуют пользовательские, уникальные элиты, которые представляют собой большую проблему и предлагают ценный лут после поражения.

Игроки получают уведомления в чате, когда происходит событие, с возможностью отслеживать здоровье и местоположение элиты по кликабельной ссылке. Если элита не побеждена в течение определенного времени, событие заканчивается и элита исчезает.

Вы можете отключить все события, открыв events.yml и установив значения `actionEventsEnabled` и `timedEventsEnabled` на `false`.

Если вы хотите отключить отдельные события, вы можете перейти в *~plugins\EliteMobs\customevents*. там вы найдете конфигурации для каждого события, и вы можете отключить любое событие, открыв его конфигурацию и установив значение `isEnabled` на `false`.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_event_boss.jpg](../../../img/wiki/eminfo_event_boss.jpg)

</details>

</div>

## Гильдия авантюристов

Гильдия авантюристов - это дополнительный мир-хаб, который вы можете установить, а также набор команд, которые могут использовать игроки.

Если мир-хаб не установлен, то игрокам придется использовать команды, в противном случае выполнение команд с установленным миром-хабом телепортирует игроков в мир-хаб, и там они могут взаимодействовать с NPC вместо того, чтобы вводить команды.

Какие команды? В EliteMobs есть несколько команд, которые игроки могут использовать для продажи и покупки предметов, ремонта предметов, зачарования предметов и многого другого. Узнайте больше о том, какие команды могут использовать игроки [здесь]($language$/elitemobs/permissions_and_commands.md&section=npc-commands).

Для получения дополнительной информации о Гильдии авантюристов и о том, как установить мир-хаб, ознакомьтесь с [этой]($language$/elitemobs/adventurers_guild_world.md) страницей.

Вы можете отключить мир-хаб, открыв *AdventurersGuild.yml* и установив значение `guildHubIsEnabledv2` на `false`.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_ag.jpg](../../../img/wiki/eminfo_ag.jpg)

</details>

</div>

## Уровень/Ранг гильдии

По мере того как игроки прогрессируют и приобретают лучшие предметы, они в конечном итоге достигают предела, и мобы перестают сбрасывать предметы более высокого уровня, это называется ограничителем добычи уровня гильдии.

Ограничитель добычи уровня гильдии ограничивает максимальный лут, который игроки могут получить, основываясь на их уровне гильдии, и применяет ограничения по умолчанию для предметов с уровня 1 по уровень 10, с соответствующими уровнями мобов. Престижные уровни открывают более высокие уровни, предоставляя доступ к превосходному луту и более сильным мобам, обеспечивая сбалансированный игровой процесс.

Эта система в сочетании с зачарованием душевной связи смягчает проблемы с повышением уровня, поддерживает баланс сервера и способствует привязанности игроков к приобретенному луту. Вы можете прочитать больше об уровне гильдии [здесь]($language$/elitemobs/guild_tier_loot_limiter.md).

Все настройки уровня гильдии можно настроить, и они находятся в *AdventurersGuild.yml*.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_guild_tier.jpg](../../../img/wiki/eminfo_guild_tier.jpg)

</details>

</div>

## Арены

Арены - это испытания, основанные на волнах, где игроки могут вступить в бой. Один или несколько игроков могут присоединиться к арене и сражаться со все более сложными волнами врагов, причем награды улучшаются по мере продвижения испытания.

Установив мир-хаб Гильдии авантюристов, игроки получают доступ к Арене деревянной лиги, бесплатной арене, доступ к которой можно получить через взаимодействие с NPC в мире-хабе или через меню */em*.

Вы можете получить дополнительные арены, перейдя на: [Itch.io](https://magmaguy.itch.io/) или подписавшись на [Patreon](https://www.patreon.com/magmaguy).

Вы можете отключить арены, перейдя в *~plugins\EliteMobs\customarenas*, а затем открыв конфигурацию арены, например *wood_league.yml*, и найдя значение `isEnabled` и установив его на `false`.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_arena.jpg](../../../img/wiki/eminfo_arena.jpg)

</details>

</div>

## Мировые подземелья

Мировые подземелья - это дополнительный пользовательский контент, который вы можете скачать для EliteMobs. В подземельях обычно есть пользовательские элитные боссы, пользовательские миры, пользовательский лут и пользовательские силы боссов.

Все мировые подземелья - это подземелья, которые расположены в своем собственном мире, а это означает, что когда игроки получают к ним доступ, они телепортируются в мир, в котором нет ничего, кроме этого подземелья.

Существует несколько типов мировых подземелий, чтобы узнать больше о типах, нажмите [здесь]($language$/elitemobs/dungeon_packager.md&section=dungeonsizecategory).

Все мировые подземелья имеют установленный уровень, и все игроки, пытающиеся пройти подземелья, должны быть примерно на этом уровне для наилучшего опыта.

Вы можете получить подземелья, перейдя на: [Itch.io](https://magmaguy.itch.io/) или подписавшись на [Patreon](https://www.patreon.com/magmaguy). Есть несколько бесплатных подземелий, которые вы можете скачать от [сюда](https://magmaguy.itch.io/em-free-content).

Вы можете отключить отдельные подземелья, перейдя в *~plugins\EliteMobs\content_packages*, открыв конфигурацию подземелья для подземелья, которое вы хотите отключить, и установив значение `isEnabled` на `false`.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_world_dungeon.jpg](../../../img/wiki/eminfo_world_dungeon.jpg)

</details>

</div>

## Инстансные подземелья

Инстансные подземелья отличаются от мировых подземелий несколькими способами. Они являются инстансами, что означает, что новый мир динамически создается на основе чертежа, предоставляя игрокам и их друзьям приватный опыт подземелья, аналогичный тем, которые встречаются в MMO.

Инстансные подземелья предлагают различные уровни сложности с уникальными силами боссов, увеличенным здоровьем и превосходным лутом по мере повышения сложности. Они также вводят роли, позволяя игрокам принимать роли танка или DPS в зависимости от их экипировки (снаряжение, предназначенное для определенных ролей, является эксклюзивным для Инстансных подземелий). Подробнее о том, как работает сложность, читайте [здесь]($language$/elitemobs/instanced_dungeon_difficulty.md).

Кроме того, игроки могут воскрешать друг друга в Инстансных подземельях, что позволяет им быстро возобновить бой, если они будут действовать достаточно быстро.

Вы можете получить инстансные подземелья, перейдя на: [Itch.io](https://magmaguy.itch.io/) или подписавшись на [Patreon](https://www.patreon.com/magmaguy). Есть бесплатные инстансные подземелья, которые вы можете скачать от [сюда](https://magmaguy.itch.io/em-free-content).

Вы можете отключить отдельные подземелья, перейдя в *~plugins\EliteMobs\dungeonpackages*, открыв конфигурацию подземелья для подземелья, которое вы хотите отключить, и установив значение `isEnabled` на `false`.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_instanced_dungeon.jpg](../../../img/wiki/eminfo_instanced_dungeon.jpg)

</details>

</div>

## Приключения

Приключения представляют собой самый обширный дополнительный контент, доступный для EliteMobs, с огромным миром, дополненным захватывающей сюжетной линией и множеством квестов, в которые игроки могут отправиться.

Приключения с сотнями пользовательских боссов, способностей и предметов предлагают захватывающий игровой процесс. Квесты в Приключениях работают аналогично квестам в традиционных MMO, ставя перед игроками задачи, такие как победа над мобами, поиск предметов, взаимодействие с NPC или любое их сочетание.

Приключения настолько велики, что в них даже есть другие под-подземелья или под-арены.

Хотя в Приключениях обычно рекомендуется определенный диапазон уровней для игроков, игрокам рекомендуется начинать свое приключение в нижней части шкалы уровней для оптимального удовольствия.

Вы можете получить приключения, перейдя на: [Itch.io](https://magmaguy.itch.io/) или подписавшись на [Patreon](https://www.patreon.com/magmaguy).

Вы можете отключить отдельные приключения, перейдя в *~plugins\EliteMobs\dungeonpackages*, открыв конфигурацию для приключения, которое вы хотите отключить, и установив значение `isEnabled` на `false`. Приключения могут иметь дополнительные под-подземелья и под-арены, которые идут в комплекте с приключениями, поэтому убедитесь, что вы отключили и их, если вы отключаете приключение.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_adventure.jpg](../../../img/wiki/eminfo_adventure.jpg)

</details>

</div>

## Телепорты-червоточины

В EliteMobs также есть простые телепортеры из точки А в точку Б, называемые червоточинами. Вы увидите, что они в основном используются в мире-хабе Гильдии авантюристов как способ телепортировать игроков оттуда в подземелье или обратно к спавну сервера.

Обычно они имеют форму шестиугольника, куба или ромба, сделанного из частиц. Эти частицы иногда могут вызывать лаги у клиентов Bedrock, поэтому вы можете отключить эффекты частиц, открыв *Wormholes.yml* и установив `noParticlesMode` на `true`.

Вы можете создавать свои собственные червоточины и использовать их так, как вам угодно. Нажмите [здесь]($language$/elitemobs/creating_wormholes.md), чтобы узнать, как это сделать.

<div align="center">

<details> 

<summary><b>Визуальный пример</b></summary>

![eminfo_wormhole.jpg](../../../img/wiki/eminfo_wormhole.jpg)

</details>

</div>

## Пользовательский контент

EliteMobs также предлагает вам возможность создавать свой собственный контент, включая [боссов]($language$/elitemobs/creating_bosses.md), [подземелья]($language$/elitemobs/dungeon_packager.md), [способности]($language$/elitemobs/creating_powers.md), [NPC]($language$/elitemobs/creating_npcs.md), [квесты]($language$/elitemobs/creating_quests.md), [арены]($language$/elitemobs/creating_arenas.md) и многое другое! Вы можете найти руководства по созданию других типов контента, кроме перечисленных выше, в боковом меню вики.

Для наиболее простого и эффективного процесса создания контента мы рекомендуем использовать WebApp. Этот инструмент позволяет вам создавать готовые к использованию файлы конфигурации без необходимости обширного просмотра вики для обеспечения правильности, особенно если вы планируете создавать способности боссов EliteScript. Получите доступ к [WebApp здесь](https://magmaguy.com/webapp/webapp.html).

# Для админов и владельцев серверов

Этот плагин разработан для серверов выживания и подобных выживанию (таких как Skyblock, Skywars и сильно модифицированные варианты выживания).

Плагин предназначен для легкого использования путем простого перетаскивания jar-файла плагина на сервер. Настройки по умолчанию - это те, которые я использую на своих собственных серверах, и они могут меняться со временем.

**Однако!** Возможность настройки была главным приоритетом на протяжении всего процесса разработки EliteMobs. Практически каждый аспект плагина может быть переведен, настроен, отключен или изменен.

# Для других разработчиков

Несмотря на GPLV3 и открытый исходный код этого проекта, я в настоящее время не ищу и не приму никаких добавлений или изменений кода. Я приветствую форки плагина и с огромным удовольствием посмотрю, что вы с ними можете сделать; однако это мой первый масштабный проект программирования, и, следовательно, это также учебный опыт.

**Однако!** Не воспринимайте это как то, что я не принимаю никакой критики или не прислушиваюсь к отзывам - совсем наоборот, я люблю, когда люди указывают на лучшие способы выполнения того, что я сделал в плагине. Я хочу, чтобы этот проект был тем, что я написал от начала до конца, без каких-либо фрагментов кода, о которых я не знаю или которых я не понимаю.
