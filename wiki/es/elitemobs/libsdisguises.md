[![webapp_banner.jpg](../../../img/wiki/webapp_banner.jpg)](https://magmaguy.com/webapp/webapp.html)

# ¿Qué es LibsDisguises?

LibsDisguises es un plugin que permite a los servidores disfrazar cualquier entidad como cualquier otro tipo de entidad. Como ejemplo, puede disfrazar a los jugadores como ovejas o disfrazar a las ovejas como jugadores.

Hay una versión [gratuita](https://www.spigotmc.org/resources/libs-disguises-free.81/) y una versión [premium](https://www.spigotmc.org/resources/libs-disguises.32453/) de LibsDisguises. LibsDisguises fue creado y es mantenido por otros desarrolladores, así que no pida soporte para este en las secciones de soporte de EliteMobs.

# ¿Cómo puedo disfrazar una entidad como un jugador?

Para disfrazar un jefe personalizado (o un jefe regional, ¡o incluso un NPC!) como un jugador, todo lo que necesita hacer es agregar la siguiente línea al archivo de configuración del jefe:

```yml
disguise: player:nombre
```

Como ejemplo, si desea disfrazar a un jefe con el skin de mi jugador, la línea de configuración se vería así:

```yml
disguise: player:magmaguy
```

# ¿Cómo puedo disfrazar una entidad como una skin de jugador, pero no necesariamente como un jugador?

Esta es la forma más flexible de disfrazar una entidad como un jugador, ya que permite a los administradores utilizar skins en línea o incluso crear las suyas propias para disfrazar a un jefe. También es un poco más complejo de hacer.

En aras de la simplicidad, los ejemplos que se enumeran aquí asumen que va a utilizar un skin disponible públicamente en línea. Libsdisguises proporciona diferentes formas de deserializar skins, incluida una en la que coloca su propio skin personalizado en su carpeta. Consulte su documentación si no desea utilizar un skin ya disponible en línea.

### 1. Establecer el disfraz

Para el disfraz, deberá hacer algo como esto:

```yaml
disguise: custom:nombre_unico_de_su_skin
```

### 2. Generación de los datos de disfraz

Esta es la parte complicada. Empiece por crear la siguiente entrada de configuración:

```yaml
customDisguiseData: player nombre_unico_de_su_skin setskin
```

*¡Es fundamental que el nombre que establezca en disguise para nombre_unico_de_su_skin coincida con el de customDisguiseData!*

Luego, deberá deserializar un skin de jugador. La forma más fácil de hacer esto para un skin disponible públicamente en línea es usar el comando grabskin de LibsDisguises.

Digamos que quiere obtener [este skin](https://www.minecraftskins.com/skin/18512841/buff-villager/).

Para hacer esto, debe ejecutar el comando `/grabskin https://www.minecraftskins.com/uploads/skins/2021/07/28/buff-villager-18512841.png?v437`

**Nota: debe proporcionar un enlace directo al archivo de skin, y no a la página que contiene el skin. Observe a dónde apunta el enlace. En [skindex](https://www.minecraftskins.com/), puede obtener el enlace directo presionando el botón "Image Link" que está presente en la parte inferior derecha de cada skin.**

Una vez que haya hecho esto correctamente, LibsDisguises le proporcionará alrededor de 3 a 6 números que dicen "Click to copy". Si hace clic en estos, aparecerá una larga lista de números y letras. Debe asegurarse de comenzar en 1 y hacer todos los números en orden. Para copiarlos, presione ctrl-a y luego ctrl-c, luego péguelos en el archivo con ctrl-v. Una vez hecho esto, debería verse similar a esto:

```yaml
customDisguiseData: player nombre_unico_de_su_skin setskin {"id":"d1fbb77f-b184-4718-b0a2-c7ae866798d3","name":"Unknown","properties":[{"name":"textures","value":"ewogICJ0aW1lc3RhbXAiIDogMTYyNzU0ODkwMjQ0OSwKICAicHJvZmlsZUlkIiA6ICIxOTI1MjFiNGVmZGI0MjVjODkzMWYwMmE4NDk2ZTExYiIsCiAgInByb2ZpbGVOYW1lIiA6ICJTZXJpYWxpemFibGUiLAogICJzaWduYXR1cmVSZXF1aXJlZCIgOiB0cnVlLAogICJ0ZXh0dXJlcyIgOiB7CiAgICAiU0tJTiIgOiB7CiAgICAgICJ1cmwiIDogImh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvMzlmYTZkMWFlODA2YTY2OGI0OTgzYmZhY2ZkMGUzMzQ5MGE5MGU4YTZmMWE2MmEwZGQ5YzQ1YjdkYjBiNjU1MyIKICAgIH0KICB9Cn0=","signature":"P/XSvxX45MUZGc5uuDKuVgmMUk2V1HADPI84Os5J4NnmURhLeS4jL4FSeShmz0cH7sBWmMg80g9ADP33R9PcOmzbHK4hJBFt2VYLJNgSYHK6VGp6qLGXDfdAa3vRNXN7jKtsrqVEANax7Gzv3xcWARLbq1FuQ6yYdXDY8Coc02Y/POMRG/i6iACtro5DQGhr2JgbL++95UhSBFxmU82Zef3UMHLfgt7lC4vWN4c4xrOAKllzF2mwohuMmEkoKzu/6s/eu5q4J4bBH08M8UN02/yJuEH5sTy/iVJfaoPs90ZfcVdRpUZvVDZh5eXapQN1/Q9/79Pc8YOXF/20iygZ/hpvTPKP8wbMP2b1cJSyAaEIUtG9I7mG3bAXbH7mcswM1CNFF3+GEFnZI5dPxzuOelJR/t2mtVl82a4zEm9KG9Fq7iGfuK9aiWR8Yot1KeuIddPbBL8JnxHy2wW9OySjzAbs8tUI/i5KKmZmQrPH0RmHrFIuVK4C849QtRt57sQaUr1+W6Vto3r7J5jhpZ30wIIfS9hvW/ReB9rbwUQWERWie5Lchfcp7YkKbzuuaddnIjPew2IQDESlXzVW84kXtYKCs8hFgYVn27wU8jqtBCVkr0iHW7YLQTl4SFUzTFCSgAx5KSFHGm/4kqXqpHNdjS687o13MWpxrxLkV1svIp4="}],"legacy":false}
```

¡Y eso es todo! `customDisguiseData` funcionará con cualquier código de skin deserializado, por lo que si encuentra otras formas de generar el mismo código en LibsDisguises, puede usarlo aquí.

La ventaja de customDisguiseData es que es autónomo, lo que significa que no tiene que depender de jugadores en línea, jugadores con skins específicos ni nada más. ¡EliteMobs lo usa para crear todos los jefes disfrazados en los paquetes de mazmorras!

# ¿Cómo puedo disfrazar a un jefe personalizado como otro tipo de entidad?

Para disfrazar a un jefe personalizado (o un jefe regional) como otro tipo de entidad, todo lo que necesita hacer es agregar la siguiente línea al archivo de configuración del jefe:

```yml
disguise: TIPO_DE_ENTIDAD
```

Como ejemplo, si desea que su jefe personalizado esté disfrazado como una oveja, haría lo siguiente:

```yml
disguise: SHEEP
```
## ¿Cómo puedo disfrazar a un jefe personalizado como una entidad bebé?

Para disfrazar a un jefe personalizado (o un jefe regional) como una entidad bebé, todo lo que necesita hacer es agregar la siguiente línea al archivo de configuración del jefe:

```yml
disguise: HOGLIN:bebé
```
Como puede ver en este ejemplo, nuestro jefe estaría disfrazado de un Baby Hoglin.

# ¿Cómo puedo disfrazar una entidad con un disfraz personalizado?

Para disfrazar un jefe personalizado (o un jefe regional) como una entidad personalizada de LibsDisguises, primero debe crear el disfraz de LibsDisguises.

Una vez que eso esté hecho, la sintaxis correcta es:

```yml
disguise: custom:nombre_de_su_disfraz_personalizado
```

# Disfraces válidos

No hay una lista oficial de tipos de entidad válidos, pero aquí hay una lista no oficial que debería funcionar en el momento de escribir esto (3 de agosto de 2020)

<details>

<summary><b>Expandir lista</b></summary>

```
    ARMOR_STAND
    ARROW
    BAT
    BLAZE
    BOAT
    CAT
    CAVE_SPIDER
    CHICKEN
    COD
    COW
    CREEPER
    DOLPHIN
    DONKEY
    DRAGON_FIREBALL
    DROWNED
    DROPPED_ITEM
    EGG
    ELDER_GUARDIAN
    ENDER_CRYSTAL
    ENDER_DRAGON
    ENDER_PEARL
    ENDER_SIGNAL
    ENDERMAN
    ENDERMITE
    EVOKER
    EVOKER_FANGS
    EXPERIENCE_ORB
    FALLING_BLOCK
    FIREBALL
    FIREWORK
    FISHING_HOOK
    FOX
    GHAST
    GIANT
    GUARDIAN
    HOGLIN
    HORSE
    HUSK
    ILLUSIONER
    IRON_GOLEM
    ITEM_FRAME
    LLAMA
    LLAMA_SPIT
    LEASH_HITCH
    MAGMA_CUBE
    MINECART
    MINECART_CHEST
    MINECART_COMMAND
    MINECART_FURNACE
    MINECART_HOPPER
    MINECART_MOB_SPAWNER
    MINECART_TNT
    MODDED_MISC
    MODDED_LIVING
    MULE
    MUSHROOM_COW
    OCELOT
    PAINTING
    PANDA
    PARROT
    PHANTOM
    PIG
    PIG_ZOMBIE
    PIGLIN
    PILLAGER
    PLAYER
    POLAR_BEAR
    PRIMED_TNT
    PUFFERFISH
    RABBIT
    RAVAGER
    SALMON
    SHEEP
    SHULKER
    SHULKER_BULLET
    SILVERFISH
    SKELETON
    SKELETON_HORSE
    SLIME
    SMALL_FIREBALL
    SNOWBALL
    SNOWMAN
    SPECTRAL_ARROW
    SPLASH_POTION
    SQUID
    STRAY
    STRIDER
    THROWN_EXP_BOTTLE
    TIPPED_ARROW
    TRIDENT
    TRADER_LLAMA
    TROPICAL_FISH
    TURTLE
    VEX
    VILLAGER
    VINDICATOR
    WANDERING_TRADER
    WITCH
    WITHER
    WITHER_SKELETON
    WITHER_SKULL
    WOLF
    ZOGLIN
    ZOMBIE
    ZOMBIE_HORSE
    ZOMBIE_VILLAGER
    ZOMBIFIED_PIGLIN
```

</details>
