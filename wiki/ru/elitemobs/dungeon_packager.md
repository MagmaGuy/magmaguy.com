```
[![webapp_banner.jpg](../../../img/wiki/webapp_banner.jpg)](https://magmaguy.com/webapp/webapp.html)

# Что такое подземелья?

Вы можете найти информацию о подземельях, включая информацию о готовых подземельях [здесь]($language$/elitemobs/dungeons.md).

***

# Что такое упаковщик подземелий?

Упаковщик подземелий позволяет администраторам не только создавать и упаковывать подземелья, но и упаковывать любой контент EliteMobs. Это включает в себя такие вещи, как пакеты событий, пакеты моделей, арены, пакеты NPC, пакеты предметов и т. д.

<details>

<summary>Зачем использовать пакеты подземелий?</summary>

- ***Инстансированные подземелья!*** Инстансированные подземелья можно создать только через систему пакетов подземелий.
- ***Безопасные резервные копии мини-подземелий!*** Если вы создадите пакет подземелий, вы сможете развернуть и повторно развернуть его на любом сервере в любое время и по любой причине.
- ***Легко включать и выключать!*** Вы всегда можете использовать команду `/em setup` и временно или постоянно включать и выключать пакеты подземелий.
- ***Легко делиться!*** Если вы хотите поделиться своими творениями, пакеты подземелий можно просто заархивировать и отправить другим людям. Если вам интересно, есть комната Discord, посвященная творениям сообщества!
- ***Телепорты!*** Пакеты подземелий автоматически создают места для телепортации, к которым можно получить доступ на странице телепортаций меню `/em`, что может быть очень полезно во многих ситуациях.

</details>

# Создание подземелий

Следующие настройки используются для создания файла конфигурации, который должен находиться в папке `content_packages`. Эти настройки используются специально для создания подземелий и не являются обязательными, если вы просто хотите использовать упаковщик подземелий для распространения контента, не связанного с подземельями, такого как пакет предметов или событий.

## Необходимые плагины

Чтобы использовать упаковщик подземелий, вам понадобится следующий плагин:

[WorldGuard](https://dev.bukkit.org/projects/worldguard) - защищает мини-подземелье.

## Создание подземелья шаг за шагом

Раньше у EliteMobs было два основных типа подземелий: на основе мира и на основе схемы.

Подземелья на основе схемы были связаны со схемой сборки. Теперь они упразднены и больше не поддерживаются.

Все подземелья EliteMobs теперь основаны на мире.

## Обязательный файл pack.meta

Ваш пакет подземелий должен включать файл `pack.meta`, который представляет собой просто переименованный файл `.txt` с расширением `.meta`. Этот файл должен содержать только одно слово, указывающее, для какого плагина предназначен пакет (например, «elitemobs», написано строчными буквами). Файл `pack.meta` должен находиться в корневом каталоге вашего пакета, рядом со всеми другими папками.

***

### Глобальные значения

Следующие значения применяются ко всем подземельям.

<div align="center">

### isEnabled

Устанавливает, включен ли пакет подземелий.

| Ключ         |      Значения       | По умолчанию | Обязательно |
|-------------|:-----------------:|:-------:|:---------:|
| `isEnabled` | [Boolean](#boolean) | `false` |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
isEnabled: true
```

</div>

</details>

***

### name

Устанавливает имя контента. Поддерживает [Цветовые коды](#color_codes).

| Ключ         |      Значения       | По умолчанию | Обязательно |
|-------------|:-----------------:|:-------:|:---------:|
| `name` | [String](#string) | `false` |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
name: '&c[lvl 999] &aЗеленое подземелье'
```

<div align="center">

![create_packager_name.jpg](../../../img/wiki/create_packager_name.jpg)

</div>

</div>

</details>

***

### dungeonLocationType

Устанавливает тип местоположения, которое использует подземелье.

| Ключ         |        Значения         | По умолчанию | Обязательно |
|-------------|:---------------------:|:-------:|:---------:|
| `dungeonLocationType` | `WORLD` / `INSTANCED` |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
dungeonLocationType: WORLD
```

</div>

</details>

***

### contentType

Устанавливает тип подземелья.

| Ключ         |                    Значения                    | По умолчанию | Обязательно |
|-------------|:--------------------------------------------:|:-------:|:---------:|
| `contentType` | `OPEN_DUNGEON` / `INSTANCED_DUNGEON` / `HUB` |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
contentType: INSTANCED_DUNGEON
```

</div>

</details>

***

### customInfo

Устанавливает дополнительную информацию, которая появится на экране `/em setup`. Только в информационных целях. Поддерживает [Цветовые коды](#color_codes).

| Ключ         |           Значения            | По умолчанию | Обязательно |
|-------------|:---------------------------:|:-------:|:---------:|
| `customInfo` | [String List](#string_list) |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
customInfo:
- '&aЛучшее подземелье.'
- '&aСоздано: КрутымИгроком'
```

<div align="center">

![create_packager_custominfo.jpg](../../../img/wiki/create_packager_custominfo.jpg)

</div>

</div>

</details>

***

### downloadLink

Устанавливает ссылку для скачивания, когда контент не загружен. Только в информационных целях.

| Ключ         |      Значения       | По умолчанию | Обязательно |
|-------------|:-----------------:|:-------:|:---------:|
| `downloadLink` | [String](#string) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
downloadLink: http://www.example.org
```

<div align="center">

![create_packager_downloadlink.jpg](../../../img/wiki/create_packager_downloadlink.jpg)

</div>

</div>

</details>

***

### dungeonSizeCategory

Устанавливает категорию размера пакета подземелий. Только в информационных целях.

| Ключ         |   Значения    | По умолчанию | Обязательно |
|-------------|:-----------:|:-------:|:---------:|
| `dungeonSizeCategory` | Special [1] |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
dungeonSizeCategory: MINIDUNGEON
```

<div align="center">

![create_packager_size.jpg](../../../img/wiki/create_packager_size.jpg)

</div>

</div>

</details>

**Special [1]**

<details> 

<summary><b>Развернуть таблицу</b></summary>

<div align="center">

| Ключ | Описание                                                                                                                                         |
|-----|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| `LAIR`    | Логова — это тип небольшого подземелья, ориентированного на одну большую битву с боссом.  |
| `SANCTUM`    | Святилища эквивалентны инстансированным Логовам. Это означает, что они сосредоточены вокруг одной огромной битвы с боссом. |
| `MINIDUNGEON`    | Мини-подземелья — это тип подземелья среднего размера, которое обычно содержит 3-15 мини-боссов и большого босса, а также множество «мусорных» мобов, которых игроки должны «фармить» для получения монет и снаряжения. |
| `DUNGEON`    | Подземелья — это эквивалент инстансированных мини-подземелий. Это наиболее традиционный тип подземелий MMORPG, где игроки объединяются в группы и проходят через череду мусорных мобов и мини-боссов, чтобы сразиться с финальным боссом. |
| `RAID`    | Скоро!|
| `ADVENTURE`    | Приключения — это полноценные карты приключений. Они включают в себя линии квестов, NPC, большое количество мини-боссов и боссов и могут даже содержать свои собственные арены или подземелья внутри себя. |
| `ARENA`    | Арены — это зоны выживания на основе волн, в которых игроки получают награды за победу над волнами. |
| `OTHER`    | Все остальное, что не попадает в предыдущие категории. |

Более подробные описания см. в разделе [Подземелья]($language$/elitemobs/dungeons.md)

</div>

</details>

***

### protect

Устанавливает, должен ли пакет подземелий быть защищен WorldGuard.

| Ключ         |      Значения       | По умолчанию | Обязательно |
|-------------|:-----------------:|:-------:|:---------:|
| `protect` | [Boolean](#boolean) |  `true`   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
protect: true
```

</div>

</details>

***

### dungeonVersion

Устанавливает версию пакета подземелий.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `dungeonVersion` | [Integer](#integer) |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
dungeonVersion: 1
```

</div>

</details>

***

### playerInfo

Устанавливает информацию, которая отображается в меню. Поддерживает [Цветовые коды](#colorcodes).

*Работает только тогда, когда `/em` установлен в книжный режим с помощью `/em alt`.*

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `playerInfo` | [String](#string) |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
playerInfo: 'Сложность: &aКонтент для одного игрока!'
```

<div align="center">

![create_packager_playerinfo.jpg](../../../img/wiki/create_packager_playerinfo.jpg)

</div>

</div>

</details>

***

### regionEnterMessage

Устанавливает сообщение, которое появляется, когда игрок входит в зону подземелья. Поддерживает [Цветовые коды](#colorcodes).

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `regionEnterMessage` | [String](#string) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
regionEnterMessage: '&aВы вошли в подземелье!'
```

<div align="center">

![create_packager_enter.jpg](../../../img/wiki/create_packager_enter.jpg)

</div>

</div>

</details>

***

### regionLeaveMessage

Устанавливает сообщение, которое появляется, когда игрок покидает зону подземелья. Поддерживает [Цветовые коды](#colorcodes).

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `regionLeaveMessage` | [String](#string) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
regionLeaveMessage: '&aВы покинули подземелье!'
```

<div align="center">

![create_packager_leave.jpg](../../../img/wiki/create_packager_leave.jpg)

</div>

</div>

</details>

***

### hasCustomModels

Устанавливает, имеет ли пакет подземелий пользовательские модели (для ModelEngine или FreeMinecraftModels).

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `hasCustomModels` | [Boolean](#boolean) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
hasCustomModels: false
```

</div>

</details>

***

### dungeonConfigFolderName

Устанавливает имя папок, используемых для файлов, связанных с этим подземельем.

**Обязательно для инстансированных подземелий!**

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `dungeonConfigFolderName` | [String](#string) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
dungeonConfigFolderName: my_dungeon_folder
```

</div>

</details>

***

### contentLevel

Устанавливает уровень контента, который должен отображаться в меню EM.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `contentLevel` | [Integer](#integer) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
contentLevel: 20
```

</div>

</details>

***

### enchantmentChallenge

Устанавливает, должно ли подземелье быть подземельем-испытанием зачарования.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `enchantmentChallenge` | [Boolean](#boolean) | `false` |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
enchantmentChallenge: false
```

</div>

</details>

</div>

***

### Пакеты подземелий на основе мира

Следующие значения применяются только к подземельям на основе мира.

<div align="center">

***

### worldName

Устанавливает имя мира, который должен быть упакован.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `worldName` | [String](#string) |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
worldName: мой_мир_майнкрафт
```

</div>

</details>

***

### womholeWorldName

Эта функция устанавливает имя мира червоточины, который служит вторичным миром, связанным с основным миром. Он используется для таких функций, как телепортационные хабы или уникальные камеры боссов.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `womholeWorldName` | [String](#string) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
womholeWorldName: мой_мир_майнкрафт_червоточина
```

</div>

</details>

***

### environment

Устанавливает окружение мира.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `environment` | [Environment](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/World.Environment.html) |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
environment: NORMAL
```

</div>

</details>

***

### teleportLocation

Устанавливает место телепортации пакета подземелий. Это место, куда игроки будут телепортироваться при входе в подземелье.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `teleportLocation` | [String](#string) |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
teleportLocation: мой_мир_майнкрафт,-1.5,68,0.5,0.0,0.0
```

</div>

</details>

***

### allowExplosionBlockDamage

Разрешает или запрещает взрывам повреждать блоки в подземелье. Взрывы считаются элитными, поэтому любое повреждение блоков будет восстановлено в течение 2 минут.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `allowExplosionBlockDamage` | [Boolean](#boolean) |  `false`   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
allowExplosionBlockDamage: true
```

</div>

</details>

</div>

#### Инстансированные подземелья

*Инстансированные подземелья создают новый мир каждый раз, когда группа игроков хочет пройти подземелье, и удаляют его, когда оно заканчивается. Чтобы это работало правильно, вы должны поместить папку, следующую за `dungeonConfigFolderName`, в папку конфигурации `world_blueprints` EliteMobs.*

*Затем вы помещаете мир, который будете использовать, внутрь созданной вами папки, убедившись, что файл `session.lock` мира удален.*

Следующие значения применяются только к инстансированным подземельям. Обратите внимание, что все инстансированные подземелья являются мировыми подземельями, поэтому они также используют значения из мировых подземелий.

<div align="center">

***

### startLocation

Устанавливает место телепортации начальной точки инстансированного подземелья. Это место, куда игроки будут телепортированы при запуске инстансированного подземелья с помощью `/em start`.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `startLocation` | [String](#string) |  none   |    ✅      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
startLocation: мой_мир_майнкрафт,10.5,70,10.5,0.0,0.0
```

</div>

</details>

***

### permission

Устанавливает разрешение, необходимое для входа в инстанс подземелья.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `permission` | [String](#string) |  none   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
permission: elitedungeon.mypermission
```

</div>

</details>

***

### minPlayerCount

Устанавливает минимальное количество игроков, необходимое для запуска подземелья.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `minPlayerCount` | [Integer](#integer) |  `1`   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
minPlayerCount: 1
```

</div>

</details>

***

### maxPlayerCount

Устанавливает минимальное количество игроков, необходимое для запуска подземелья.

| Ключ         |  Значения  | По умолчанию | Обязательно |
|-------------|:--------:|:-------:|:---------:|
| `maxPlayerCount` | [Integer](#integer) |   `5`   |    ❌      |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
maxPlayerCount: 5
```

</div>

</details>

***

### dungeonObjectives

Устанавливает список целей подземелья, необходимых для того, чтобы подземелье считалось пройденным.

| Ключ         |           Значения            | По умолчанию | Обязательно |
|-------------|:---------------------------:|:-------:|:---------:|
| `dungeonObjectives` | [String List](#string_list) |  none   |    ✅      |

<details> 

<summary><b>Примеры</b></summary>

<div align="left">

В настоящее время существует два типа целей подземелий:

* Убить цель: `filename=boss.yml:amount=X`
* Убить процент подземелья: `clearpercentage=X.Y`

```yml
dungeonObjectives:
- filename=dungeon_final_boss.yml
- filename=dungeon_miniboss_one.yml
- filename=dungeon_miniboss_two.yml
```

```yml
dungeonObjectives: 
- clearpercentage=0.8
```

</div>

</details>

***

### difficulties

Устанавливает список сложностей в инстансированном подземелье.

**Обязательно для инстансированных подземелий!**

| Ключ         |   Значения    | По умолчанию | Обязательно |
|-------------|:-----------:|:-------:|:---------:|
| `difficulties` | Special [1] |  none   |    ❌      |

<details> 

<summary><b>Примеры</b></summary>

<div align="left">

```yml
difficulties:
- levelSync: 25
  id: 0
  name: normal
- levelSync: 20
  id: 1
  name: hard
- levelSync: 15
  id: 2
  name: mythic
```

<div align="center">

![create_packager_difficulty.jpg](../../../img/wiki/create_packager_difficulty.jpg)

</div>

</div>

</details>

**Special [1]**

<details>

<summary><b>Развернуть таблицу</b></summary>

<div align="center">

Установка сложностей инстансированного подземелья автоматически создаст различные варианты сложности при входе в подземелье.

Имена сложностей, установленные здесь, будут использоваться в папке пользовательских боссов, где вы можете установить, какие способности имеют боссы в зависимости от сложности.

Сложности представлены в виде списка со следующими полями:

|     Ключ     | Описание                                                                                                                                                                                                                                                    | Значения | Обязательно |
|:-----------:|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|:---------:|
|   `name`    | Название сложности для игроков.                                                                                                                                                                                                                            |[String](#string)        |     ✅     |
|    `id`     | ID сложности, используемый в пользовательских боссах и пользовательских предметах для функции на основе сложности.                                                                                                                                  |[String](#string)        |     ✅     |
| `levelSync` | Устанавливает уровень синхронизации уровней, если таковой имеется. Синхронизация уровней повышает уровень всего снаряжения игрока до установленного значения, что делает невозможным получение игроками слишком высокого уровня для подземелья и сохраняя его актуальным для последующих прохождений. На основе системы синхронизации уровней Final Fantasy 14. |[Integer](#integer)        |     ❌     |


</div>

</details>

</div>

***

## Использование файла пакета подземелий meta_pack.yml для больших подземелий.
```
```
Иногда вы можете работать над большим подземельем, которое включает в себя другие, меньшие подземелья, позволяя игрокам перемещаться между ними через основной мир подземелий. Отличным примером этого является приключенческое подземелье EliteMobs Primis.

Primis имеет обширный мир, где игроки могут исследовать и выполнять квесты, но он также включает в себя два инстансированных подземелья в своем мире, одно из которых служит финальной битвой с боссом. В подобных случаях будет несколько файлов пакетов подземелий, даже если все они принадлежат одному общему подземелью.

Для управления этим мы используем мета-файл пакета подземелий. Этот файл действует как центральный каталог, определяя основное подземелье и перечисляя весь дополнительный контент подземелий, связанный с ним.

Давайте подробнее рассмотрим, как структурирован мета-пакет подземелий Primis:

```yaml
isEnabled: true
name: '&2[000-020] Приключение Примис!'
customInfo:
- Обучающее приключение для игроков
- новичков в EliteMobs!
downloadLinkV2: https://discord.gg/9f5QSka
dungeonSizeCategory: LAIR
environment: NORMAL
protect: true
contentType: META_PACKAGE
containedPackages:
- primis_adventure.yml
- primis_blood_temple_sanctum.yml
- primis_gladius_invasion_dungeon.yml
setupMenuDescription:
- '&2Мягкое обучающее приключение для игроков с уровнями 0-20!'
- '&2Приключения — это огромные карты с квестами,'
- '&2множество боссов и NPC, среди прочего!'
- '&2Также есть пользовательские модели!'
dungeonVersion: 21 #добавлен мета-файл пакета подземелий
```

Как видите, файл мета-пакета подземелий очень похож на обычный пакет подземелий, с несколькими ключевыми отличиями. Параметр `contentType:` установлен в значение `META_PACKAGE`, и есть дополнительная настройка под названием `containedPackages:`. Этот параметр перечисляет все остальные пакеты подземелий, которые являются частью большего подземелья.

При создании мета-пакета обязательно включите параметр `containedPackages:` и перечислите каждый пакет подземелий, который является частью вашего большего подземелья. Это гарантирует, что все правильно связано и организовано в рамках общей структуры.

При указании версии вашего подземелья, все управление версиями должно осуществляться через мета-пакет. Это связано с тем, что мета-пакет служит основным пакетом, который определяет версию всего подземелья, а также является пакетом, используемым для отображения информации в меню `/em setup`.

Имейте в виду, что отдельные подземелья, перечисленные в мета-пакете, могут по-прежнему отображаться в меню `/em teleport`. Чтобы этого не произошло, вам нужно будет вручную отключить параметры телепортации для каждого из этих подземелий в соответствующих файлах конфигурации.

Например, в случае с подземельем Primis:

Отключите записи телепортации в меню для `primis_blood_temple_sanctum.yml` и `primis_gladius_invasion_dungeon.yml`.
Оставьте параметры телепортации включенными для `primis_adventure.yml`, поскольку он служит основным центром, откуда игроки начинают свое путешествие и получают доступ к другим подземельям.
Эта настройка обеспечивает бесперебойную работу для игроков, сохраняя при этом правильную структуру и функциональность системы подземелий.

При именовании файла мы рекомендуем следующую схему именования:

`your_dungeon_name_meta_pack.yml`

***

# Рекомендуемые значения боссов

## Создание обычного моба в подземелье

Мы рекомендуем оставить настройку normalizedCombat установленной в значение true. Эта настройка нормализует всех мобов, чтобы они масштабировались одинаково по здоровью и урону, независимо от типа их сущности.

```yaml
normalizedCombat: true
healthMultiplier: 1.0 #4 удара до убийства
damageMultiplier: 1.0 #1.5 сердец урона
```

Конечно, вот пересмотренная версия с сохраненной четкостью и форматированием:

**Примечание: учитывая, что `1.0` является значением по умолчанию для здоровья и урона, вы можете просто опустить определение `healthMultiplier` или `damageMultiplier` и установить для `normalizedCombat` значение `true`.**

## Создание мусорных пачек

Мусорные пачки многочисленны, но не очень опасны:

```yaml
normalizedCombat: true
healthMultiplier: 0.7 #3 удара до убийства
damageMultiplier: 0.5 #0.5 сердец урона
```

## Создание подкреплений

Подкрепления должны умирать очень легко, но представлять опасность с точки зрения урона (эти значения рекомендуются для 4+ сущностей ближнего боя, фактическое использование может отличаться):

```yaml
normalizedCombat: true
healthMultiplier: 0.25 #1 удар до убийства
damageMultiplier: 0.6 #1 сердце урона
```

## Создание мини-боссов

Мини-боссы должны удерживать свои позиции и представлять собой механическое испытание для игроков. Это должно быть испытание навыков, которое длится некоторое время, но не должно быть чем-то чрезвычайно смертельным:

```yaml
normalizedCombat: true
healthMultiplier: 3.0 #10 ударов до убийства
damageMultiplier: 1.2 #2 сердца урона
```

## Создание боссов

Боссы — это настоящее испытание, кульминация нарастания в подземелье и настоящее испытание навыков, когда на кону стоит все. Сражения должны быть долгими, и смерть должна быть постоянной угрозой.

```yaml
normalizedCombat: true
healthMultiplier: 7.0 #23 удара до убийства
damageMultiplier: 1.4 #2.5 сердца урона
```

**Эти рекомендуемые значения являются всего лишь приблизительными оценками, и окончательные значения должны быть скорректированы в соответствии с конкретными сражениями.**

**Это особенно важно для финальных боссов подземелий; вы можете значительно превысить рекомендуемое значение 7.0 для healthMultiplier, чтобы придать последней битве ощущение эпичности.**

***

# Упаковка контента EliteMobs для распространения

Наконец, вы, вероятно, захотите упаковать свое подземелье либо для хранения, либо для распространения.

EliteMobs имеет систему импорта, которая позволяет администраторам быстро импортировать, устанавливать и удалять контент. [Вы можете посмотреть, как это работает, здесь.]($language$/elitemobs/setup.md)

## Обрезка миров

Иногда вам может потребоваться уменьшить размер вашего мира Minecraft, чтобы сделать его легче и, следовательно, легче распространять. Это можно сделать с помощью [плагина WorldBorder](https://www.spigotmc.org/resources/worldborder-1-15.80466/). Несмотря на то, что плагин указан как поддерживающий MineCraft только до версии 1.19, он без проблем работает в последней версии MineCraft по состоянию на 25 января 2024 г.

<details>
<summary>Совет</summary>
Если вы делаете это в первый раз, может быть хорошей идеей создать резервную копию своего мира на случай, если что-то пойдет не так.
</details>

После установки плагина перейдите к середине мира или к конкретной области, которую вы хотите обрезать. Затем выполните команду `/wb set x`, где `x` представляет приблизительный размер радиуса, который вы хотите для своей области.

<details>
<summary>Совет</summary>
Если <code>/wb</code> не работает для вас, попробуйте <code>/worldborder:wb</code>.
</details>

После выполнения этой команды облетите края вашего мира, чтобы убедиться, что граница мира была правильно установлена и покрывает нужный размер. Вы узнаете о достижении края границы мира, когда вас оттолкнут назад, сопровождаемое сообщением в чате.

![trim_pic_1.jpg](../../../img/wiki/trim_pic_1.jpg)

На изображении выше мы хотим обрезать мир вокруг фиолетовых блоков, оставив вокруг них всего несколько чанков. Чтобы добиться этого, мы стоим посередине фиолетовой области на красных квадратах и выполняем команду `/wb set 50`, устанавливая границу мира чуть дальше фиолетовой области.

Затем мы используем команду `/wb trim [freq] [pad]`, установив частоту на 200, а отступ на 20. Отступ определяет, сколько чанков должно быть оставлено вокруг границы мира (фиолетовой области), а частота определяет, сколько чанков должно обрабатываться в секунду. После выполнения команды `/wb trim 200 20` нам будет предложено подтвердить, выполнив команду `/wb trim confirm`. Мы подтверждаем действие, и через некоторое время наш мир будет обрезан, что уменьшит его размер и сделает его более удобным для распространения.

Теперь вы можете удалить границу мира с помощью `/wb clear all` или просто оставить ее, если хотите.

## Обрезка папки мира

В папке вашего мира есть несколько файлов и папок, которые мы можем отбросить, поскольку плагины не используют их все. Это уменьшит размер вашего мира и облегчит его распространение.

Для среды НОРМАЛЬНОГО мира:

Чтобы подготовить свой мир, сохраните следующие файлы и папки:

1. Папка **region**
2. **raids.dat** из папки **data** (убедитесь, что он помещен внутрь папки **data** при копировании)
3. файл **level.dat**

Вы можете безопасно удалить все остальные файлы и папки, расположенные в папке мира. Это правильно настроит ваш мир для НОРМАЛЬНОЙ среды.

Для сред мира NETHER и THE_END:

Чтобы подготовить свой мир, сохраните следующие файлы и папки:

1. папка **region** внутри папки **DIM-1** (убедитесь, что она помещена внутрь папки **DIM-1** при копировании)
2. **raids.dat** из папки **data** (убедитесь, что он помещен внутрь папки **data** при копировании)
3. файл **level.dat**

Вы можете безопасно удалить все остальные файлы и папки, расположенные в папке мира. Это правильно настроит ваш мир для сред NETHER и THE_END.

## Запуск команды упаковки

EliteMobs имеет команду **`/em package <dungeonName> <version>`**. Эта команда просматривает все папки конфигурации EliteMobs и автоматически упаковывает весь контент в папках, которые соответствуют `dungeonName`, в zip-файл и обычную папку в папке `exports` EliteMobs.

***По этой причине настоятельно рекомендуется хранить контент, который вы хотите упаковать, в папках с тем же именем, что и имя вашего пакета.*** В противном случае вам придется вручную собирать и упаковывать файлы в файловую структуру для распространения.

## Добавление файла пакета подземелий

Если вы создаете подземелье, вам нужно будет вручную добавить файл пакета подземелий в только что созданную папку в папке exports. Ваш файл конфигурации пакета подземелий должен соответствовать формату, описанному выше, и должен быть помещен в папку под названием `content_packages`. [Проверьте структуру файлов для получения дополнительной информации об этом.](#file-structure).

**Не забудьте заархивировать свое подземелье после завершения!**

## Структура файлов

Если вы все сделали правильно, структура файлов должна быть похожа на этот пример, где мы назвали подземелье `my_cool_dungeon`:

<details>
<summary>Пример структуры файлов my_cool_dungeon</summary>

- my_cool_dungeon.zip
    * content_packages
        * my_cool_dungeon.yml <- Сюда помещается файл конфигурации пакета вашего подземелья
    * worldcontainer
        * [Здесь находятся ваши папки мира]
    * wormholes
        * my_cool_dungeon
            * [Здесь находятся ваши червоточины]
    * npcs
        * my_cool_dungeon
            * [Здесь находятся ваши NPC]
    * customtreasurechests
        * my_cool_dungeon
            * [Здесь находятся ваши сундуки с сокровищами]
    * customquests
        * my_cool_dungeon
            * [Здесь находятся ваши квесты]
    * customitems
        * my_cool_dungeon
            * [Здесь находятся ваши пользовательские предметы]
    * custombosses
        * my_cool_dungeon
            * [Здесь находятся ваши пользовательские боссы]
    * customarenas
        * my_cool_dungeon
            * [Здесь находятся ваши пользовательские арены]
    * powers
        * my_cool_dungeon
            * [Здесь находятся ваши пользовательские способности]
    * world_blueprints
        * my_cool_dungeon
            * [Здесь находится ваша папка мира, используемая для инстансированных подземелий]
    * customevents
        * my_cool_dungeon
            * [Здесь находятся ваши пользовательские события]
    * customspawns
        * my_cool_dungeon
            * [Здесь находятся ваши пользовательские спауны]
    * models
        * [Здесь находятся ваши модели в формате bbmodel ModelEngine, принимает папки]

</details>

Это позволяет большинству пользователей перетаскивать файлы прямо на свой сервер, и они сразу же начинают работать.

***Важно: при упаковке для распространения убедитесь, что вы СНАЧАЛА УДАЛИЛИ МИНИ-ПОДЗЕМЕЛЬЕ! Вы не хотите распространять установленные мини-подземелья, вы хотите, чтобы администраторы устанавливали их на своих серверах!***

# Делитесь пакетами подземелий, которые вы создали, с сообществом

Discord содержит раздел [#community_dungeons](https://discord.gg/7Pnd7EjdZq "#community_dungeons"), где люди могут делиться своими творениями Minidungeon. Не стесняйтесь вносить свой вклад!
```