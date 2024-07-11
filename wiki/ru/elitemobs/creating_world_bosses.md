[![webapp_banner.jpg](../../../img/wiki/webapp_banner.jpg)](https://magmaguy.com/webapp/webapp.html)

# Создание Мировых Боссов
*Мировые боссы также иногда называются Региональными боссами.*
## Что это такое?

Мировые боссы - это  Custom Bosses, которые созданы для появления в определенном месте с определенной задержкой. Это также боссы, которые используются в подземельях. Хотя в этом разделе мы будем говорить о создании Мировых боссов для использования вне подземелий.

## Для чего они нужны?

Мировые боссы позволяют игрокам столкнуться с фиксированным вызовом, зная, что награда будет стоить усилий.

## Что нужно, чтобы сделать Мирового босса?

1. **Местоположение**. Рекомендуется использовать комнату босса радиусом примерно 15 блоков (30 блоков в ширину) из-за  радиуса  аггро  Minecraft. Кроме того, убедитесь, что ландшафт защищен регионом [WorldGuard](https://dev.bukkit.org/projects/worldguard) (чтобы игроки не могли создавать ловушки), и что ландшафт не может быть использован для получения преимущества в бою.
2. **Время появления**. Таймер появления - это важно. Я не рекомендую делать время появления менее 30 минут, иначе появление босса будет менее значимым событием. 1 час - это довольно хорошее время, но вы также можете сделать так, чтобы босс появлялся раз в день или даже раз в неделю.
3. **Время побега**. Чем дольше время появления, тем дольше должно быть время побега. Также учитывайте, что время побега должно быть достаточно длинным, чтобы люди могли спокойно бросить вызов боссу. Таймеры побега важны, если вы не хотите, чтобы игроки могли совершать самоубийственный рывок, чтобы убить босса. Это не обязательно, и даже не рекомендуется, если вы хотите создать огромных боссов, которые появляются раз в неделю.
4. **Custom Boss**. Мировые боссы - это всего лишь  Custom Bosses  с  custom правилами появления. Убедитесь, что вы выбрали способности с хорошей совместимостью с боем в масштабе рейда.
5. **Интересный лут**. Главный фактор привлекательности Мировых боссов, помимо вызова, - это лут. Убедитесь, что игроки могут получить из него что-то, чего они просто не могут получить из других источников.
6. **Тема**. Хороший региональный босс должен иметь тему, тематическое местоположение и тематический лут.

## Опции настройки  Custom Boss  для Мировых боссов:

Эти настройки добавляются к обычным файлам конфигурации  Custom Boss. [Здесь можно найти обширную страницу вики об этом]($language$/elitemobs/creating_bosses.md).

<div align="center">

***

### isRegionalBoss

Определяет, является ли босс региональным. Региональные боссы - это другое название Мировых боссов, поэтому вам нужно установить это значение как `true`.

| Ключ       |       Значения        | По умолчанию |
|-----------|:-------------------:|:-------:|
| `isRegionalBoss` | [Boolean](#boolean) | `false` |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
isRegionalBoss: true
```

</div>

</details>

***

### spawnLocations

Точки появления должны задаваться из игры с помощью команды `/em addSpawnLocation <filename.yml>`.

Хотя можно добавлять местоположения вручную из конфигурации, я не рекомендую этого делать, так как это слишком просто сделать ошибку.

| Ключ              |           Значения            | По умолчанию |
|------------------|:---------------------------:|:-------:|
| `spawnLocations` | [String List](#string_list) |  none   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

Местоположения в файлах конфигурации (для опытных пользователей) Файлы конфигурации регионального босса хранят все экземпляры этого регионального босса в одном файле, храня одновременно несколько точек появления и таймеры появления.

На практике это означает, что эта запись:

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

содержит 7 разных региональных боссов в разных местах и с разными таймерами появления.

Давайте разберем детали, взглянув на первого регионального босса:

```yaml
- elitemobs_sewer_maze,-70.17178578884845,168.2,-173.17112099568718,-271.24023,64.19999:1610710903931
```

Так как это соответствует формату `world,x,y,z,pitch,yaw:unixTimeStamp`, босс появляется в мире `elitemobs_sewer_maze` в точке x = `-70.17178578884845`, y = `168.2`, z = `-173.17112099568718`, pitch = `-271.24023`, yaw = `64.19999`.

Unix-метка времени хранит время, в формате Unix-времени, когда босс снова появится. Это используется для хранения времени появления при перезагрузках. Если вы хотите узнать, какое время это соответствует, вы можете найти в Интернете множество инструментов для преобразования времени Unix в реальное время.

Если вы хотите, чтобы определенный босс снова появился после перезагрузки или перезапуска, вам просто нужно очистить запись `:unixTimeStamp`.

</div>

</details>

***

### spawnCooldown

Время (в минутах) до появления босса снова.

**Примечание: для крупных боссов рекомендуется более длительное время появления!**.

| Ключ       |       Значения        | По умолчанию |
|-----------|:-------------------:|:-------:|
| `spawnCooldown` | [Integer](#integer) |  none   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
spawnCooldown: 20
```

</div>

</details>

***

### leashRadius

Расстояние, на которое босс может уйти от своей точки появления, прежде чем его обратно телепортируют. Это не позволяет игрокам увести босса в место, где с ним будет легче сражаться.

**Примечание: старайтесь избегать создания зон боя, которые требуют поводка короче 20 блоков, так как это усложнит бой.**

| Ключ       |       Значения        | По умолчанию |
|-----------|:-------------------:|:-------:|
| `leashRadius` | [Double](#double) |  none   |

<details> 

<summary><b>Пример</b></summary>

<div align="left">

```yml
leashRadius: 30
```

</div>

</details>

***

### Transitive Blocks

Также известны как `onSpawnBlockStates` и `onRemoveBlockStates`.

Эти значения позволяют региональным боссам генерировать блоки при вступлении в бой и удалять их при исчезновении, то есть когда они либо убегают из-за времени ожидания, либо умирают.

**Это то, как вы можете заставить боссов открывать или закрывать двери/зоны или даже изменять арену во время боя, если используете их с фазовыми боссами!**

| Ключ       |          Значения          | По умолчанию |
|-----------|:------------------------:|:-------:|
| `onSpawnBlockStates` | См. Подробное объяснение |  none   |


| Ключ       | Values  | По умолчанию |
|-----------|:-------:|:-------:|
| `onRemoveBlockStates` | См. Подробное объяснение |  none   |

<details> 

<summary><b>Подробное объяснение</b></summary>

<div align="left">

**Все блоки относительны к месту появления. Убедитесь, что у вас есть окончательное место появления, прежде чем начинать задавать блоки.**

</br>Если вы уже создали большую зону  Transitive Block  и теперь вам нужно переместить босса, но вы не хотите переделывать  Transitive Blocks. Тогда можно использовать действие EliteScript  [Teleport]($language$/elitemobs/elitescript_actions.md&section=teleport)  для перемещения босса в нужное место после появления. Имейте в виду, что вам нужно будет соответствующим образом отрегулировать  leash.

Из-за сложности установки блоков не рекомендуется делать это вручную. Используйте следующие команды, чтобы сделать это:

- /em registerblocks <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em registerblocksedit <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em registerblocksarea <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em registerblocksareaedit <regional\_boss\_file.yml> <on\_spawn/on\_remove>
- /em cancelblocks

Давайте разберем это.

**/em registerblocks <regional\_boss\_file.yml> <on\_spawn/on\_remove>**

Самая базовая команда. Это переключатель, который вы запускаете один раз, чтобы начать, и еще раз, чтобы подтвердить. Как и для всех других команд, вы выбираете, задаете ли эти блоки для модификации для состояния `on_spawn` или `on_remove`.

Если регистрируется on\_spawn, то это модифицирует блоки, когда босс появляется или появляется снова. Если регистрируется on\_remove, то это модифицирует блоки, когда босс умирает или истекает время, используя механику времени ожидания  Custom Boss.

Чтобы зарегистрировать блоки, просто поставьте или удалите блоки, которые вы хотите модифицировать, пока эта настройка активна.

**/em registerblocksedit <regional\_boss\_file.yml> <on\_spawn/on\_remove>**

Если вы хотите модифицировать уже установленные блоки, вы можете использовать эту команду. Работает очень похоже на `/em registerblocks <regional_boss_file.yml> <on_spawn/on_remove>`.

**/em registerblocksarea <regional\_boss\_file.yml> <on\_spawn/on\_remove>**

Как и `/em registerblocks <regional_boss_file.yml> <on_spawn/on_remove>`, это позволяет вам регистрировать блоки, но позволяет выбирать их, получая два диаметрально противоположных угла (то же самое, что и выбор области worldedit / worldguard), вместо того, чтобы выбирать блоки по отдельности.

Для безопасности есть ограничение в 200 блоков (по умолчанию, можно изменить в config.yml) для региональных выборов. Имейте в виду, что каждый блок модифицируется в том же такте, поэтому если вы модифицируете много ландшафта, вы, вероятно, начнете видеть большие скачки лагов при выполнении этих модификаций.

**/em registerblocksareaedit <regional\_boss\_file.yml> <on\_spawn/on\_remove>**

Работает так же, как `/em registerblocksedit`, но для областей. Можно использовать, чтобы превысить ограничение в 200 (по умолчанию) блоков регистрации для областей.

**/em cancelblocks**

В любое время, если во время регистрации блоков была допущена ошибка, вы можете выполнить эту команду, чтобы отменить регистрацию. Она отменит все изменения, которые вы начали регистрировать в этой редактировании/регистрации.

</div>

</details>

</div>

***

## Советы профессионалов по созданию хорошей большой битвы с региональным боссом

1. **Подумайте о том, как способности вашего  Custom Boss  взаимодополняют друг друга.** Вы не хотите, чтобы ваш босс большую часть времени стоял, потому что он что-то кастует, так как это может фактически сделать бой очень легким. Также вы не хотите, чтобы у босса были только дальние атаки, а не ближние, или наоборот, если только вы не проектируете что-то очень конкретное. Важно тестировать игру.


2. **Здоровье - много здоровья**. Множитель здоровья, вероятно, должен быть около 10, если вы хотите, чтобы люди действительно объединялись для боя с боссом.


3. **Урон - не слишком много**. EliteMobs по умолчанию уже очень опасны, а способности, как правило, еще опаснее. Вместо того, чтобы увеличивать урон до предела, рассмотрите возможность использования способностей, чтобы босс бил сильнее.


4. **Эксплойты, везде**. Убедитесь, что ландшафт не может быть использован для получения преимущества. Поместите босса в закрытую комнату, чтобы игроки не могли стрелять в него издалека. Способность к неуязвимости к стрелам, вероятно, очень важна для многих Мировых боссов, поскольку мобы Minecraft не могут переносить выстрелы из чанков, поэтому, если вы хотите разрешить атаку луком, убедитесь, что луки нельзя эксплуатировать.


5. **Знайте плагин**. Есть много хитростей, как победить EliteMobs, например, как некоторые способности можно парировать, используя щиты, а другие нужно парировать, уклоняясь или даже временно убегая от босса. Чем больше вы знаете о том, как работают способности и как их парировать, тем лучше будут боссы, которых вы создаете.


