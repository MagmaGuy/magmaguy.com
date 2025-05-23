```markdown
# Перезарядки скриптов элиты

Перезарядки определяют количество времени, которое должно пройти, прежде чем босс сможет выполнить тот же скрипт или любую другую способность*.

- примечание: на некоторые способности в настоящее время перезарядки не влияют.

Перезарядки имеют два значения:

## local (локальная)

`local` устанавливает время в тиках, прежде чем тот же скрипт сможет сработать снова. Пример:

Пример

```yaml
local: 60
```

Позволяет способности сработать снова через 3 секунды.

## global (глобальная)

`global` устанавливает время в тиках, прежде чем любой другой скрипт или способность смогут сработать снова\[1\]. Пример:

Пример

```yaml
global: 20
```

Запрещает всем другим способностям запускаться в течение 1 секунды.

\[1] на некоторые старые способности в настоящее время это не влияет, работа над этим продолжается.

**Примечание: увеличивая локальную перезарядку и уменьшая глобальную, вы можете гарантировать, что босс будет чередовать свои доступные способности!** Никогда не делайте глобальную перезарядку длиннее, и я рекомендую оставлять хотя бы одну секунду локальной перезарядки, чтобы дать другим способностям шанс сработать.

Кроме того, если ваша способность имеет определенную длительность, в течение которой она активна, вам следует использовать эту систему, чтобы предотвратить одновременное выполнение других способностей, которые могут потенциально испортить вашу способность.

### Запуск скриптов один раз с перезарядками
Чтобы гарантировать, что скрипты срабатывают только один раз, при этом используя [Событие]($language$/elitemobs/elitescript_events.md), которое может происходить несколько раз во время боя, установите локальную перезарядку на большое число, например `99999`. Этот пример демонстрирует концепцию:

<div align="center">

<details>

<summary><b>Пример</b></summary>

<div align="left">

```yaml
eliteScript:
  SetMeOnFireOnlyOnce:
    Events:
    - EliteMobDamagedByPlayerEvent
    Actions:
    - action: SET_ON_FIRE
      duration: 60
      Target:
      targetType: DIRECT_TARGET
    Cooldowns:
    local: 99999
    global: 50
```
В этом сценарии `EliteMobDamagedByPlayerEvent` запускает действие `SET_ON_FIRE`. Без перезарядок действие активировалось бы каждый раз, когда игрок бьет моба.

Однако, с локальной перезарядкой, установленной на `99999`, действие будет срабатывать только каждые `99999` тиков (83 минуты).

</div>

</details>

</div>
```