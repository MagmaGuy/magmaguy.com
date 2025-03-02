# Événements Elite Script

Les EliteScripts sont basés sur des événements. Cela signifie qu'ils sont lancés lorsqu'un événement spécifique est
déclenché. Voici les événements actuellement valides:

| Événement                      |                              Détails                               | Cible Directe [[?]($language$/elitemobs/elitescript_targets.md)] |
|--------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------:|
| EliteMobDamagedByEliteMobEvent |                Élite endommagée par une autre élite                |                                ❌                                 |
| EliteMobDamagedByPlayerEvent   |                   Élite endommagée par un joueur                   |                   Joueur infligeant des dégâts                   |
| EliteMobDamagedEvent           |                Élite endommagée par n'importe quoi                 |                                ❌                                 |
| EliteMobDeathEvent             |                          Mort d'une élite                          |                                ❌                                 |
| EliteMobEnterCombatEvent       |                Élite entre en combat avec un joueur                |                         Joueur engageant                         |
| EliteMobExitCombatEvent        |                        Élite sort du combat                        |                                ❌                                 |
| EliteMobHealEvent              |                     Élite complètement soignée                     |                                ❌                                 |
| EliteMobSpawnEvent             |                       Apparition d'une élite                       |                                ❌                                 |
| EliteMobTargetPlayerEvent      |                       Élite cible un joueur                        |                           Joueur ciblé                           |
| PlayerDamagedByEliteMobEvent   |                     Élite endommage un joueur                      |                         Joueur endommagé                         |
| ElitePhaseSwitchEvent          |            Boss apparait lors d'un changement de phase             |                                ❌                                 |
| ZoneEnterEvent                 | Entité entre dans la zone. Nécessite la configuration d'une zone ! |                Entité qui est entrée dans la zone                |
| ZoneLeaveEvent                 |   Entité quitte la zone. Nécessite la configuration d'une zone !   |                   Entité qui a quitté la zone                    |

**Remarque: « Élite » désigne toute entité agressive générée par le plugin, qu'il s'agisse d'un renfort, d'un boss ou
autre.**
**Remarque: Les événements ZoneEnterEvent et ZoneLeaveEvent sont coûteux en termes de calcul. Veuillez les utiliser avec
parcimonie!**

`Cible Directe` est utilisée par les Cibles de script, plus
d'informations [ici]($language$/elitemobs/elitescript_targets.md).

`ZoneEnterEvent` et `ZoneLeaveEvent` sont des événements spéciaux qui permettent aux scripteurs de déclencher des
actions en fonction des entités qui entrent et quittent des zones définies dans les scripts. La CIBLE_DIRECTE de
ZoneEnterEvent et ZoneLeaveEvent est l'entité qui est entrée ou sortie (cela signifie que vous ne pouvez pas utiliser la
cible directe comme cible de la zone), et en raison du fonctionnement de la logique interne, seuls les points absolus (
coordonnées spécifiques) et les points relatifs au boss peuvent être utilisés pour analyser les entrées et les sorties (
impossible d'utiliser des zones qui ciblent les joueurs).

Il ne peut y avoir qu'une seule section [Événement]($language$/elitemobs/elitescript_events.md) par script. Cependant, plusieurs événements peuvent être définis comme déclencheurs d'un script :

<div align="center">

<details> 

<summary><b>Exemple</b></summary>

<div align="left">

```yaml
eliteScript:
  Example:
    Events:
    - EliteMobDamagedByPlayerEvent
    - EliteMobTargetPlayerEvent
    Actions:
    - action: PUSH
      Target:
        targetType: SELF
      vValue: 0,.3,0
    Cooldowns:
      local: 60
      global: 20
```

Ce script ferait sauter l'élite lorsqu'elle est touchée par un joueur ou lorsqu'elle cible un joueur.

</div>

</details>

</div>
