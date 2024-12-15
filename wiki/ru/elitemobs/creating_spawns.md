[![webapp_banner.jpg](../../../img/wiki/webapp_banner.jpg)](https://magmaguy.com/webapp/webapp.html)

# Что такое пользовательские спавны?

Пользовательские спавны используются событиями и глобальными подкреплениями для настройки того, как, где и когда событие должно порождать босса для этого события.

События и глобальные подкрепления устанавливают, какой спавн они используют, записывая имя его файла.

# Создание пользовательских спавнов

Пользовательские спавны помещаются в папку `customspawns`. Один пользовательский спавн может использоваться несколькими событиями одновременно, поэтому вам не нужно создавать один для каждого события.

Вот пример пользовательского спавна:

```yaml
isEnabled: true
validWorldTypes:
- NORMAL
- CUSTOM
bypassWorldGuard: false
isSurfaceSpawn: true
```

## Создание спавна в любом месте
Чтобы сделать спавн, который может происходить **где угодно**, ваша конфигурация должна выглядеть следующим образом:

```yml
isEnabled: true
canSpawnInLight: true
```
Эта конфигурация позволяет мобам появляться в любом месте, в любом мире, в любое время и в любую фазу луны.

Если вас интересует создание более настраиваемого спавна, продолжайте читать ниже.

## Значения

<div align="center">

***

### isEnabled

Устанавливает, включен ли спавн.

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

Устанавливает нижний уровень y (высота карты), используемый для спавна.

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

Устанавливает верхний уровень y (высота карты), используемый для спавна.

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

Устанавливает список миров, в которых может происходить пользовательский спавн. Этот параметр можно пропустить, чтобы разрешить **все** ваши миры.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `validWorlds` | [Список строк](#string_list) |  нет   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
validWorlds:
- WORLD
- FUN_LAND
```

*Если вы хотите, чтобы все ваши миры были действительными, вы можете просто не использовать этот параметр или отформатировать его следующим образом:*

```yml
validWorlds: []
```

</div>

</details>

***

### validWorldEnvironments

Устанавливает список допустимых окружений мира, в которых может происходить пользовательский спавн. Этот параметр можно пропустить, чтобы разрешить **все** окружения.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `validWorldEnvironments` | [Список окружений](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/WorldType.html) |  нет   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
validWorldEnvironments:
- FLAT
- LARGE_BIOMES
```

*Если вы хотите, чтобы все окружения были действительными, вы можете просто не использовать этот параметр или отформатировать его следующим образом:*

```yml
validWorldEnvironments: []
```

</div>

</details>

***

### validBiomes

Устанавливает список допустимых биомов, в которых может происходить пользовательский спавн. Этот параметр можно пропустить, чтобы разрешить **все** биомы.

| Ключ       |           Значения            | По умолчанию |
|-----------|:---------------------------:|:-------:|
| `validBiomes` | [Список биомов](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Biome.html) |  нет   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
validBiomes:
- DESERT
- MUSHROOM_FIELDS
```

*Если вы хотите, чтобы все биомы были действительными, вы можете просто не использовать этот параметр или отформатировать его следующим образом:*

```yml
validBiomes: []
```

</div>

</details>

***

### earliestTime

Устанавливает самое раннее игровое время, в которое может произойти пользовательский спавн.

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

Устанавливает самое позднее игровое время, в которое может произойти пользовательский спавн.

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

Устанавливает фазу луны, при которой может произойти пользовательский спавн.

| Ключ       |   Значения    | По умолчанию |
|-----------|:-----------:|:-------:|
| `moonPhase` | Специальный [1] | `24000` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
moonPhase: 24000
```

</div>

</details>

**Специальный [1]**

<details> 

<summary><b>Развернуть таблицу</b></summary>

| Фаза луны        | Предпросмотр  |
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

Устанавливает, будет ли пользовательский спавн обходить системы защиты, такие как WorldGuard.

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

Указывает, может ли пользовательский спавн происходить на блоках, освещенных источниками света.

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

Устанавливает, может ли пользовательский спавн происходить только на поверхности мира.

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

Устанавливает, может ли пользовательский спавн происходить только под землей.

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
