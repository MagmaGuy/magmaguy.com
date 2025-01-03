[![webapp_banner.jpg](../../../img/wiki/webapp_banner.jpg)](https://magmaguy.com/webapp/webapp.html)

# Système de Scripting EliteMobs

La page suivante explique comment créer des Scripts Elite !

Il s'agit d'une fonctionnalité avancée qui nécessite une connaissance approfondie d'EliteMobs.

**Remarque : Les Scripts Elite peuvent être ajoutés en tant que fichiers de pouvoir ou aux fichiers de boss
personnalisés !** S'ils sont utilisés comme fichiers de pouvoir, vous pouvez les ajouter comme pouvoirs normaux aux boss
en utilisant le paramètre de configuration [powers]($language$/elitemobs/creating_bosses.md&section=powers) des Boss
Personnalisés, comme d'habitude.

## Ajouter un Script Elite

Pour commencer à ajouter un Script Elite à un boss, ajoutez l'entrée suivante au fichier du boss :

```yml
eliteScript:
```

**Remarque : Ce qui suit est extrêmement sensible à la casse et aux espaces ! Assurez-vous que vos espaces, sauts de
ligne et la mise en forme générale correspondent aux exemples !**

Maintenant que vous avez déclaré le début de votre script, vous pouvez ajouter votre script spécifique. Pour cet
exemple, nous allons créer un script appelé `Exemple` :

```yml
eliteScript:
  Exemple:
```

Les Scripts Elite ont 5 sections différentes : `Événements`, `Conditions`, `Zones`, `Actions` et `Temps de Recharge`.
Seules les `Actions` sont obligatoires.

Jetons un coup d'œil à un exemple simple :

```yml
eliteScript:
  Exemple:
    Events:
    - EliteMobDamagedByPlayerEvent
    Actions:
    - action: PUSH
      Target:
        targetType: SELF
      vValue: 0,0.5,0
    Cooldowns:
      local: 60
      global: 20
```

Ce script fait qu'un élite est repoussé vers le haut lorsqu'il est touché par un joueur, et ne le fera plus pendant 3
secondes (et empêchera les autres pouvoirs de se déclencher pendant 1 seconde en raison des paramètres que nous avons
définis dans la section Temps de Recharge).

Maintenant que vous connaissez le format général de la structure des scripts, il est temps d'apprendre ce que vous
pouvez faire avec chaque section !

----

# Événements

[Événements]($language$/elitemobs/elitescript_events.md)

Cliquez sur le lien ci-dessus pour apprendre à utiliser les événements !

# Cibles

[Cibles]($language$/elitemobs/elitescript_targets.md)

Cliquez sur le lien ci-dessus pour apprendre à utiliser les cibles !

# Actions

[Actions]($language$/elitemobs/elitescript_actions.md)

Cliquez sur le lien ci-dessus pour apprendre à utiliser les actions !

# Zones

[Zones]($language$/elitemobs/elitescript_zones.md)

Cliquez sur le lien ci-dessus pour apprendre à utiliser les zones !

# Conditions

[Conditions]($language$/elitemobs/elitescript_conditions.md)

Cliquez sur le lien ci-dessus pour apprendre à utiliser les conditions !

# Temps de Recharge

[Temps de Recharge]($language$/elitemobs/elitescript_cooldowns.md)

Cliquez sur le lien ci-dessus pour apprendre à utiliser les temps de recharge !

----

## Ajouter plusieurs Scripts Elite

Vous pouvez avoir plusieurs actions sur un événement, mais que faire si vous voulez plusieurs scripts sur le même boss ?
C'est aussi simple que de créer une nouvelle entrée de script ! Développons l'exemple précédent et ajoutons-y un autre
script :

```yml
eliteScript:
  Exemple:
    Events:
    - EliteMobDamagedByPlayerEvent
    Actions:
    - action: PUSH
      Target:
        targetType: SELF
      vValue: 0,0.5,0
    Cooldowns:
      local: 60
      global: 20
  Exemple2:
    Events:
    - PlayerDamagedByEliteMobEvent
    Actions:
    - action: SET_ON_FIRE
      Target:
        targetType: DIRECT_TARGET
    Cooldowns:
      local: 200
      global: 60
```

Dans cet exemple, nous avons ajouté un deuxième script appelé Exemple2. Exemple2 mettra le feu au joueur qui est blessé
par le boss, ceci est dû au fait que le targetType est défini
sur [DIRECT_TARGET]($language$/elitemobs/elitescript_targets.md&section=target-types). </br>Le temps de recharge pour ce
script est fixé à 200 ticks, ce qui signifie que le boss ne pourra mettre le feu aux joueurs que toutes les 10 secondes.

## Créer des pouvoirs autonomes

Les pouvoirs autonomes sont presque entièrement composés par le Script Elite. Il n'y a que deux champs qui sont
facultatifs. N'oubliez pas que pour que les pouvoirs autonomes fonctionnent, ils doivent être placés dans le
dossier `~plugins/EliteMobs/powers`. </br>Exemple de pouvoir autonome :

```yml
isEnabled: true
powerType: UNIQUE
eliteScript:
  Exemple:
    Events:
    - EliteMobDamagedByPlayerEvent
    Actions:
    - action: PUSH
      Target:
        targetType: SELF
      vValue: 0,.3,0
    Cooldowns:
      local: 60
      global: 20
```

### isEnabled

Comme partout ailleurs dans le plugin, définit si le pouvoir est activé.

### powerType

Le type de pouvoir définit comment le pouvoir est attribué. Les valeurs sont :

- `UNIQUE` : Le pouvoir ne sera appliqué qu'aux boss personnalisés qui ont le pouvoir défini dans la section des
  pouvoirs.
- `DEFENSIVE` / `MISCELLANEOUS` / `OFFENSIVE` : TOUT élite pourra obtenir ces pouvoirs, et ils compteront pour un
  sous-ensemble spécifique de pouvoirs.
- `MAJOR_ZOMBIE`, `MAJOR_SKELETON`, `MAJOR_BLAZE`, `MAJOR_ENDERMAN`, `MAJOR_GHAST` : Seuls les élites du type d'entité
  adéquat pourront apparaître naturellement avec ces pouvoirs, et ils compteront pour les pouvoirs majeurs.
