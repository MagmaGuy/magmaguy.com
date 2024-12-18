## Генераторы

Генераторы - самая мощная часть системы конфигурации BetterStructures. По умолчанию существует 27 генераторов, которые в совокупности управляют более чем 200 постройками, распространяемыми BetterStructures в настоящее время, и, хотя вы можете создавать свои собственные генераторы, вы также можете использовать существующие в качестве ярлыка.

Генераторы сообщают плагину, где именно должны появляться объекты, и определяют таблицы добычи. Названия генераторов по умолчанию также выбраны таким образом, чтобы было очень легко догадаться, что они делают.

Единственным обязательным полем для генераторов является параметр `structureType`, который указывает плагину, предназначено ли здание для появления в небе, на небольшой глубине под землей, на большой глубине под землей, на поверхности или на поверхности жидкости.

***

### isEnabled

Устанавливает, включен ли генератор.

***

### structureType

Устанавливает, какой тип структуры имеет постройка. **Обратите внимание, что вы можете создать список из нескольких типов!**

Допустимыми значениями типа структуры являются:

***

#### surface

```yml
structureType: 
- SURFACE
```

Наземные структуры появляются на поверхности мира. Единственным исключением является Нижний мир, где они появляются в точках, которые плагин считает достаточно похожими на поверхность.

***

#### sky

```yml
structureType: 
- SKY
```

Небесные структуры появляются на высоте от 80 до 120 блоков над воздухом, что настраивается в config.yml. Единственным исключением является Нижний мир, где они появляются в точках, которые плагин считает достаточно похожими на воздух.

***

#### underground_shallow

```yml
structureType: 
- UNDERGROUND_SHALLOW
```

Мелкие подземные структуры появляются между y=0 и y=60 в обычном мире, между y=60 и y=120 в Нижнем мире и на любой допустимой подземной высоте в Крае.

_**Примечание:** Вы заметите, что есть два подземных параметра. Это связано с тем, что наличие только одного параметра приводит к очень редкому появлению подземных структур, поскольку в Minecraft много подземного пространства, и игроки часто упускают подземные структуры просто потому, что не прокопали к ним._ Это также гарантирует равномерное распределение по разным глубинам._

***

#### underground_deep

```yml
structureType: 
- UNDERGROUND_DEEP
```

Глубокие подземные структуры появляются между y=-64 и y=0 в обычном мире, между y=0 и y=60 в Нижнем мире и не появляются в Крае.

***

#### liquid_surface

```yml
structureType: 
- LIQUID_SURFACE
```

Структуры на поверхности жидкости будут появляться на жидкостях. В случае обычного мира они будут появляться на воде и почти всегда в океанах. В случае Нижнего мира они будут появляться в лавовых озерах. Они не будут появляться в Крае.

***

### lowestYLevel

Устанавливает самый низкий уровень Y (высоту), на котором будет появляться структура.

***

### highestYLevel

Устанавливает самый высокий уровень Y (высоту), на котором будет появляться структура.

***

### validWorlds

Устанавливает список миров, в которых будет появляться структура. **Если список отсутствует, он будет использовать все миры, разрешенные плагином**, если иное не ограничено (например, типом окружения или биомами).

***

### validWorldEnvironments

Устанавливает список типов миров, в которых будет появляться структура. **Если список отсутствует, он будет использовать все типы миров, разрешенные плагином**. Допустимые значения: `NORMAL`, `NETHER`, `END` и `CUSTOM`.

***

### validBiomes

Устанавливает список допустимых биомов, в которых будет появляться структура. **Если список не определен, предполагается, что каждый биом допустим!**.

Для этого необходимо использовать список биомов, как определено в [Spigot API](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/Biome.html).

***

### treasureFilename

Устанавливает файл сокровищ, который будет использовать генератор. Это определяет, что появляется в сундуках для всех построек, использующих этот генератор, если другое значение не установлено в [параметре `treasureFile` конфигурации схемы]($language$/betterstructures/creating_structures.md&section=treasurefile).
