Если у вас есть вопрос, которого нет в этом списке, ***посмотрите на боковую панель***, чтобы узнать, есть ли для него отдельная страница
в вики!

# FAQ по настройке и установке

### Как настроить пользовательские модели?

<details>
<summary>
Информация
</summary>

Существует два разных плагина, которые обрабатывают "Пользовательские модели".

- LibsDisguises (включая бесплатную версию) позволяет маскировать мобов под других мобов или под пользовательские скины игроков. Если вы видите пользовательского босса в маскировке игрока, то для маскировки используется LibsDisguises. Чтобы эта конкретная функция работала, вам нужно будет скачать LibsDisguises.

- FreeMinecraftModels (и ModelEngine R3, хотя ModelEngine больше не рекомендуется) позволяет маскировать мобов под любую пользовательскую модель с очень небольшими ограничениями. FreeMinecraftModels позволяет делать это бесплатно и рекомендуется. Для работы пользовательских моделей вам придется использовать FreeMinecraftModels или ModelEngine R3 (не R4). FreeMinecraftModels можно запускать вместе с ModelEngine, поэтому вы также можете просто запустить оба.
<br>Если вы установили FreeMinecraftModels/ModelEngine, а пользовательские модели по-прежнему не работают, возможно, вы установили контент до установки плагина моделей. Чтобы убедиться, что это не проблема, переимпортируйте контент EliteMobs с пользовательскими маскировками и установите его снова.

</details>

### Консоль / EliteMobs сообщает, что вы используете неправильную версию WorldGuard

<details>
<summary>
Информация
</summary>

Если EliteMobs сообщает, что WorldGuard не установлен, это означает, что вы используете неправильную версию WorldGuard для вашей серверной платформы. WorldGuard очень чувствителен к тому, какую версию вы используете, и имеет разные версии для серверного программного обеспечения.

- Вы можете скачать версию WorldGuard для Spigot / Paper отсюда: https://dev.bukkit.org/projects/worldguard - Убедитесь, что она совместима с вашей версией Minecraft!

</details>

### Червоточины / Арены / NPC, похоже, работают неправильно сразу после установки

<details>
<summary>
Информация
</summary>

Если червоточины / арены / NPC, похоже, не работают должным образом сразу после установки контента, вам следует выполнить команду `/em reload`. Всегда полезно запускать ее после установки контента EliteMobs.

</details>

### Боссы подземелий не появляются снова после их убийства

<details>
<summary>
Информация
</summary>

В большинстве случаев это происходит просто потому, что у некоторых боссов большие таймеры возрождения. У Тени Связывателя Миров самый длинный таймер возрождения - 1 неделя в реальной жизни. У боссов логов обычно таймер возрождения составляет 4 часа. Все остальное обычно имеет таймер возрождения 5-30 минут. Вы можете отредактировать таймер возрождения пользовательского босса в его файле конфигурации в папке `~/plugins/EliteMobs/custombosses`.

</details>

### Боссы подземелий никогда не появлялись после установки

<details>
<summary>
Информация
</summary>

Это почти наверняка связано с вмешательством стороннего плагина. Проверьте следующее:
- Ваш мир находится на мирном уровне сложности? Мобы не появляются на мирном уровне сложности.

- Защищен ли ваш регион от появления мобов? Подземелья EliteMobs обрабатывают собственную защиту региона через WorldGuard, вам не нужно защищать миры подземелий EliteMobs, на самом деле это может предотвратить появление, если используются неправильные флаги.

- Есть ли другой плагин, который мешает боссам EliteMobs появляться или удаляет их? Эти конфликты часто будут отображаться в консоли, поэтому проверьте журналы консоли.

</details>

### Плагин не заполняет автоматически команды для контента, который я только что установил

<details>
<summary>
Информация
</summary>

Автозаполнение команд обрабатывается CloudCommandFramework и обновляет предложения команд только **после перезапуска сервера**. К сожалению, я ничего не могу с этим поделать.

</details>

### Как использовать переводы EliteMobs?

<details>
<summary>
Информация
</summary>

Вы можете изменить язык EliteMob, выполнив команду `/em language <languagename>.yml`. чтобы использовать перевод плагина по умолчанию, созданный и управляемый сообществом EliteMobs

Чтобы добавить язык, которого нет в плагине, или настроить существующий язык, рекомендуется использовать `custom_language.yml`.

Языковые файлы генерируют свое содержимое только при переключении языка!

Если вы нарушите форматирование файла yml, что очень легко сделать по ошибке, файл будет сброшен! ***Обязательно сохраните локальную резервную копию вашего перевода, если вы переводите контент вручную!***

Легче переводить языковой файл на веб-сайте перевода сообщества, так как он сам обрабатывает форматирование! Он также автоматически предлагает переводы. Вы можете найти его здесь: https://crowdin.com/project/elitemobs

Напоминаем, что если вы переводите, если вы используете специальные символы, такие как `&`, для начала значения конфигурации, вы должны заключить это значение в кавычки, например \"&cCool value\"! В противном случае файл будет поврежден, и ваш прогресс будет сброшен. Вы можете использовать линтер для проверки правильности yml-файла - просто вставьте содержимое yml сюда: <https://www.yamllint.com/>

</details>

# FAQ по совместимости EliteMobs и BetterStructures

### Могу ли я получить структуры в BetterStructure с боссами из EliteMobs?

<details>
<summary>
Информация
</summary>

Да, пакеты святилищ BetterStructures - это именно такой контент. Вы можете скачать пакеты святилищ с [itch.io](https://magmaguy.itch.io/).

</details>

### Почему святилища защищены WorldGuard и как это предотвратить?

<details>
<summary>
Информация
</summary>

Структуры святилищ EliteMobs по умолчанию защищены WorldGuard, чтобы игроки не строили механизмы для злоупотребления боевой системой Minecraft в зоне боя.

Защита автоматически удаляется после победы над боссом.

У каждого святилища есть точки входа, которые игроки должны раскопать, чтобы найти, если они находятся под землей.

Если вы не хотите использовать защиту WorldGuard, вы можете отключить ее в файле конфигурации BetterStructures config.yml.

</details>

### Почему святилища появляются без элиты в них?

<details>
<summary>
Информация
</summary>

Это может произойти, если вы установите святилища BetterStructures до установки EliteMobs. Чтобы исправить это, переимпортируйте и переустановите святилища на свой сервер **после** установки EliteMobs.

</details>

### Могу ли я использовать святилища, не используя EliteMobs

<details>
<summary>
Информация
</summary>

Святилища были созданы специально для борьбы с боссами, которые в них находятся, но если вам нужны только боевые арены для эстетики, вы можете просто запустить пакеты святилищ без установленной EliteMobs.

</details>

# FAQ по совместимости EliteMobs и FreeMinecraftModels

### Совместим ли FreeMinecraftModels с EliteMobs?

<details>
<summary>
Информация
</summary>

Да. Плагин FreeMinecraftModels был создан специально для EliteMobs и EternalTD.

</details>

### Как установить пользовательские модели EliteMobs?

<details>
<summary>
Информация
</summary>

Вы можете скачать пользовательские модели для EliteMobs с https://www.patreon.com/magmaguy и https://magmaguy.itch.io/. После того, как вы их установили, **вам придется объединить пакет ресурсов**, сгенерированный FreeMinecraftModels в его выходной папке, с официальным пакетом ресурсов от EliteMobs, если вы хотите использовать официальный пакет ресурсов и распространять его среди игроков, размещая его в Интернете.

</details>

### Как установить пользовательские модели EliteMobs?

<details>
<summary>
Информация
</summary>

Вы можете скачать пользовательские модели для EliteMobs с https://www.patreon.com/magmaguy и https://magmaguy.itch.io/. После того, как вы их установили, вам **придется объединить пакет ресурсов**, сгенерированный FreeMinecraftModels в его выходной папке, с официальным пакетом ресурсов от EliteMobs, если вы хотите использовать официальный пакет ресурсов и распространять его среди игроков, размещая его в Интернете.

</details>


# FAQ по совместимости EliteMobs и ResurrectionChest

### Работает ли EliteMobs с ResurrectionChest?

<details>
<summary>
Информация
</summary>

Да. ResurrectionChest был создан специально для контента EliteMobs и полностью совместим.

</details>

# FAQ по совместимости с другими плагинами

### Могу ли я использовать EliteMobs с плагином, аналогичным MCMMO или AureliumSkills?

<details>
<summary>
Информация
</summary>

Да. При этом вы можете отключить бонусное здоровье от системы престижа EliteMobs.

</details>

### Могу ли я использовать EliteMobs с другим плагином пользовательских предметов?

<details>
<summary>
Информация
</summary>

Да. Если вы хотите, чтобы боссы выбивали определенные предметы из этого плагина, вы устанавливаете команды на смерть, которые будут запускаться и давать игрокам предметы таким образом. Однако нет реального способа сбалансировать EliteMobs с любой системой предметов, которую вы используете. Элиты переходят от 7 очков здоровья к сотням тысяч очков здоровья, и поэтому другие плагины предметов либо будут безумно перегружены, либо невероятно недогружены. EliteMobs уже имеет встроенную систему предметов и не требует каких-либо внешних плагинов предметов.

</details>

# Другой FAQ

### Выполнить команду при смерти Элитного моба или выдать добычу/награды из других плагинов при смерти Элитного моба?

[Информация доступна здесь.]($language$/elitemobs/creating_bosses.md&section=ondeathcommands)

### Поддержка Vault?

[Информация доступна здесь.]($language$/elitemobs/vault.md)

### PlaceholderAPI плейсхолдеры?

[Информация доступна здесь.]($language$/elitemobs/placeholders.md)

### Использовать флаги WorldGuard, чтобы разрешить EliteMobs в некоторых местах, а в других нет?

[Информация доступна здесь.]($language$/elitemobs/worldguard_flags.md)

### Могу ли я сделать так, чтобы 100% появляющихся мобов были Элитными мобами?

Это ужасная идея, но вы можете получить доступ к файлу конфигурации `MobCombatSettings.yml` и
отредактировать `eliteMobsSpawnPercentage`, чтобы установить процент появления Элитных мобов.

### Могу ли я создавать пользовательские силы?

[Информация доступна здесь.]($language$/elitemobs/creating_powers.md)

### Могу ли я создавать пользовательские зачарования?

Это есть в нашем списке дел, и скоро должно появиться, но в настоящее время это невозможно.

### Могу ли я создавать пользовательские эффекты зелий?

Единственный способ сделать это - выучить Java и написать их самостоятельно. В этом случае вы могли бы также изменить
Исходный код EliteMobs.

### Как отключить частицы червоточины?

Чтобы отключить частицы червоточины, перейдите к *~plugins\EliteMobs\Wormholes.yml*, затем найдите `noParticlesMode` и
измените значение на `false`.

### Как отредактировать червоточину в AG spawn, чтобы телепортировать игроков туда, куда я хочу?

<div align="center">

![faq_ag_wormhole.jpg](../../../img/wiki/faq_ag_wormhole.jpg)

</div>

Вы можете сделать это, открыв *plugins\EliteMobs\wormholes\adventurers_guild_wormhole.yml*.

Затем найдите следующую настройку
`location2: your_world_here,0.5,64,0.5,0,0`
и измените значения на ваше предпочтительное местоположение.

Не забудьте выполнить `/em reload`, чтобы изменения вступили в силу.

### Как развязать предметы?

Единственный способ удалить привязку к душе из предметов - это использовать Свитки Развязывания. Подробнее об этом
[здесь]($language$/elitemobs/soulbind.md).

### Как объединить пакеты ресурсов?

Можно объединять пакеты ресурсов вручную, но мы рекомендуем использовать онлайн-инструмент, например [merge.elmakers](https://merge.elmakers.com/), для объединения ваших пакетов ресурсов.

### Каковы плейсхолдеры команд EliteMobs?

| Плейсхолдер |          Детали           |
| --- |:--------------------------:|
| `$player` | Отображаемое имя игрока |
| `$bossName` |  Отображаемое имя босса  |
| `$bossLevel` |     Уровень босса      |

### Что мне делать, чтобы отключить принудительный пакет ресурсов?

Эта настройка на самом деле находится в файле `server.properties`. Обычно вы можете найти этот файл в корневом каталоге вашего сервера. После открытия файла найдите настройку `require-resource-pack` и измените значение на `false`, чтобы отключить принудительный пакет ресурсов.

### Как отключить события?

Если вы хотите отключить такие события, как гоблин оружия, гоблин талисманов и т.д. Затем вы можете открыть *~plugins\EliteMobs\events.yml*, затем найдите настройки `actionEventsEnabled`, `timedEventsEnabled` и установите их на `false`.

### Как отредактировать мир подземелья или мир Гильдии Искателей Приключений?

Начиная с EliteMobs 9, EliteMobs больше не полагается на WorldGuard для защиты подземелий и контента. Чтобы временно обойти эту защиту, используйте команду `/em protection bypass`.

Если вы хотите навсегда отключить защиту для определенного подземелья, выполните следующие действия:

1. Перейдите к *plugins/EliteMobs/content_packages/*.
2. Найдите файл *dungeon_config.yml* для подземелья, которое вы хотите изменить.
3. Откройте файл конфигурации и найдите настройку `protect:`.
4. Измените значение на `false`, чтобы отключить защиту.
