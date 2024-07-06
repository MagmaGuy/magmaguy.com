[![webapp_banner.jpg](../../../img/wiki/webapp_banner.jpg)](https://magmaguy.com/webapp/webapp.html)

# Что такое  Custom Spawns?

Custom Spawns используются событиями и глобальными подкреплениями для определения того, как, где и когда событие должно создать босса для этого события.

События и глобальные подкрепления задают, какую точку появления они используют, записывая ее имя файла.

# Создание  Custom Spawns

Custom Spawns  находятся в папке `customspawns`. Одну  Custom Spawn  можно использовать одновременно для нескольких событий, поэтому вам не нужно создавать ее для каждого события.

Вот пример  Custom Spawn:

```yaml
isEnabled: true
validWorldTypes:
- NORMAL
- CUSTOM
bypassWorldGuard: false
isSurfaceSpawn: true
```

## Создание точки появления, доступной везде
Чтобы создать точку появления, которая может быть в **любом месте**, ваша конфигурация должна быть похожа на следующую:

```yml
isEnabled: true
canSpawnInLight: true
```
Эта конфигурация позволяет мобам появляться в любом месте, в любом мире, в любое время и при любой фазе луны.

Если вы хотите создать более настраиваемую точку появления, читайте дальше.

## Значения

<div align="center">

***

### isEnabled

Включает или выключает точку появления.

| Ключ       |       Значения        | По умолчанию |
|-----------|:-------------------:|:-------:|
| `isEnabled` | [Boolean](#boolean) | `true`  |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
isEnabled: true
```

</div>

</details>

***

### lowestYLevel

Самый низкий уровень Y (высота карты), используемый.

| Ключ       |       Значения        | По умолчанию |
|-----------|:-------------------:|:-------:|
| `lowestYLevel` | [Integer](#integer) |   `0`   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
lowestYLevel: 0
```

</div>

</details>

***

### highestYLevel

Самый высокий уровень Y (высота карты), используемый.

| Ключ       |       Значения        | По умолчанию |
|-----------|:-------------------:|:-------:|
| `highestYLevel` | [Integer](#integer) |  `320`  |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
highestYLevel: 320
```

</div>

</details>

***

### validWorlds

Список миров, где может быть  Custom Spawn.  Если эта настройка не задана,  **все ваши миры будут считаться допустимыми**.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `validWorlds` | [String List](#string_list) |  none   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
validWorlds:
- WORLD
- FUN_LAND
```

*Если вы хотите, чтобы все ваши миры были допустимыми, просто не используйте эту настройку или отформатируйте ее таким образом:*

```yml
validWorlds: []
```

</div>

</details>

***

### validWorldEnvironments

Список допустимых сред миров, где может быть  Custom Spawn.  Если эта настройка не задана,  **все среды будут считаться допустимыми**.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `validWorldEnvironments` | [Список сред](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/WorldType.html) |  none   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
validWorldEnvironments:
- FLAT
- LARGE_BIOMES
```

*Если вы хотите, чтобы все среды были допустимыми, просто не используйте эту настройку или отформатируйте ее таким образом:*

```yml
validWorldEnvironments: []
```

</div>

</details>

***

### validBiomes

Список допустимых биомов, где может быть  Custom Spawn.  Если эта настройка не задана,  **все биомы будут считаться допустимыми**.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `validBiomes` | [Список биомов](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Biome.html) |  none   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
validBiomes:
- DESERT
- MUSHROOM_FIELDS
```

*Если вы хотите, чтобы все среды были допустимыми, просто не используйте эту настройку или отформатируйте ее таким образом:*

```yml
validBiomes: []
```

</div>

</details>

***

### earliestTime

Самое раннее время в игре, когда может произойти  Custom Spawn.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `earliestTime` | [Integer](#integer) |   `0`   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
earliestTime: 0
```

</div>

</details>

***

### latestTime

Самое раннее время в игре, когда может произойти  Custom Spawn.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `latestTime` | [Integer](#integer) | `24000` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
latestTime: 24000
```

</div>

</details>

***

### moonPhase

Самое раннее время в игре, когда может произойти  Custom Spawn.

| Ключ       |   Значения    | По умолчанию |
|-----------|:-----------:|:-------:|
| `moonPhase` | Special [1] | `24000` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
moonPhase: 24000
```

</div>

</details>

**Special [1]**

<details> 

<summary><b>Expand Table</b></summary>

| Фаза Луны        | Предпросмотр  |
|-------------------|:--------:|
| `NEW_MOON`        |    🌑    |
| `WAXING_CRESCENT` |    🌒    |
| `FIRST_QUARTER`   |    🌓    |
| `WAXING_GIBBOUS`  |    🌔    |
| `FULL_MOON`       |    🌕    |
| `WANING_GIBBOUS`  |    🌖    |
| `WANING_CRESCENT` |    🌘    |

</details>

***

### bypassWorldGuard

Определяет, будет ли  Custom Spawn  обходить системы защиты, такие как WorldGuard.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `bypassWorldGuard` | [Boolean](#boolean) | `false` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
bypassWorldGuard: false
```

</div>

</details>

***

### canSpawnInLight

Определяет, может ли  Custom Spawn  происходить на блоках, освещенных источниками света.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `canSpawnInLight` | [Boolean](#boolean) | `false` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
canSpawnInLight: false
```

</div>

</details>

***

### isSurfaceSpawn

Определяет, может ли  Custom Spawn  происходить только на поверхности мира.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `isSurfaceSpawn` | [Boolean](#boolean) | `false` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
isSurfaceSpawn: false
```

</div>

</details>

***

### isUndergroundSpawn

Определяет, может ли  Custom Spawn  происходить только под землей.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `isUndergroundSpawn` | [Boolean](#boolean) | `false` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
isUndergroundSpawn: false
```

</div>

</details>

</div>

