Конечно, вот перевод на русский язык с сохранением форматирования Markdown:

# ***Прежде чем начать!***

FreeMinecraftModels (FMM) в настоящее время находится в **активной разработке**! Это означает, что некоторые функции еще не готовы и активно дорабатываются.

Однако на данный момент ядро плагина полностью функционально — преобразование файлов bbmodel, генерация ресурс-паков, спавн сущностей в игре и управление их анимациями, возможность размещать постоянные пропы — все это в основном работает.

Рассмотрите возможность поддержать разработку на https://www.patreon.com/magmaguy !

Содержимое экспортируемого ресурс-пака лицензируется по лицензии CC0 со стороны FreeMinecraftModels, все права не защищены. Вы можете свободно использовать, распространять, изменять его для любых целей без ограничений и необходимости указания авторства.

# Использование этого плагина

## Что FreeMinecraftModels (FMM) может сделать для администраторов серверов Minecraft?

Он может:

- Импортировать модели в форматах .bbmodel или fmmodel (собственный формат FFM)
- Генерировать ресурс-паки с моделями, превышающими обычные ограничения ресурс-паков Minecraft (до 112x112x112 единиц или 7x7x7 блоков в игре, функционально неограниченно при использовании нескольких костей)
- Отображать эти модели в игре, отправляя специфические пакеты, совместимые с Bedrock, клиентам Bedrock, а также отправляя сущности отображения (display entities) клиентам Java 1.19.4+
- Анимировать эти модели так, как они были настроены в Blockbench
- Обрабатывать анимации состояний по умолчанию без необходимости использования других плагинов (ходьба, бездействие, смерть, атака, спавн)
- Обрабатывать хитбоксы, которые вращаются вместе с базовой сущностью и имеют разные оси X и Z
- Управлять тремя типами моделей: статическими, динамическими и пропами
    - Пропы являются постоянными и могут быть размещены в мире таким образом, что сохранятся даже после перезапуска сервера, и можно распространять карты с пропами на другие серверы
    - Динамические модели предназначены для моделей, которым для функционирования требуется базовая живая сущность, идеально подходят для плагинов пользовательских боссов или питомцев
    - Статические модели предназначены для непостоянных моделей, которые не должны перемещаться, то есть, по сути, для временных украшений или эффектов

### Как добавить существующую модель?

Чтобы импортировать модель, просто перетащите файл .bbmodel в папку `imports` и выполните команду `/fmm reload`. Это сгенерирует файл .fmmodel в папке `models` и добавит модель в ресурс-пак в папке `outputs`.

***Вам потребуется использовать этот ресурс-пак для корректного отображения модели!*** Это обычный ресурс-пак, поэтому все, что вам нужно сделать, это поместить его в папку с ресурс-паками. Серверы Minecraft имеют способ размещения ресурс-паков. Я рекомендую использовать мой плагин [ResourcePackManager](https://www.spigotmc.org/resources/resource-pack-manager.118574/), который автоматически получает файлы и размещает их удаленно для вас, даже объединяя их с файлами других плагинов.

### Как просмотреть модель в игре?

Важно отметить, что хотя FreeMinecraftModels может использоваться как отдельный плагин для просмотра пропов (по сути, пользовательских моделей, которые можно размещать в мире), плагин обычно проявляет себя наилучшим образом в сочетании с такими плагинами, как [EliteMobs](https://www.spigotmc.org/resources/elitemobs.40090/), где модели активно используются для чего-то конкретного, в данном случае для боев с боссами.

Существует три типа моделей: статические, динамические и пропы.
- Пропы являются постоянными и могут быть размещены в мире таким образом, что сохранятся даже после перезапуска сервера, и можно распространять карты с пропами на другие серверы
- Динамические модели предназначены для моделей, которым для функционирования требуется базовая живая сущность, идеально подходят для плагинов пользовательских боссов или питомцев
- Статические модели предназначены для непостоянных моделей, которые не должны перемещаться, то есть, по сути, для временных украшений или эффектов

#### Просмотр статических моделей в игре

Для просмотра статических моделей в игре используйте команду `/fmm spawn static <id>`, где id — это имя файла модели, в нижнем регистре и без расширения файла.

#### Просмотр динамических моделей в игре

Для просмотра динамических моделей в игре используйте команду `/fmm spawn dynamic <id>`, где id — это имя файла модели, в нижнем регистре и без расширения файла.

#### Просмотр пропов в игре

Для просмотра пропов в игре используйте команду `/fmm spawn prop <id>`, где id — это имя файла модели, в нижнем регистре и без расширения файла.

## Что FreeMinecraftModels (FMM) может сделать для моделлеров?

FMM следует стандартным правилам ресурс-паков для их генерации. Кроме того, он старается быть максимально совместимым с моделями, совместимыми с ModelEngine, чтобы попытаться стандартизировать создание моделей для разных плагинов.

### Особенности / ограничения генерации моделей

Если вы когда-либо создавали модели для ModelEngine, вы будете знакомы со многими ограничениями генерации ресурс-паков Minecraft:

#### **Кубы:**

Кубы здесь такие же, как и в Blockbench, это кубы, из которых состоит модель.

- Кубы могут иметь размер до 112x112x112 "пикселей" (единиц Blockbench) или 7x7x7 блоков в игре (обычные ограничения Minecraft обходятся с помощью размеров отображения, скоро будут еще больше обходиться для 1.19.4+ благодаря сущностям отображения)
- Допустимые повороты для кубов: 0, 22.5, -22.5, 45 и -45. Другие повороты не работают.
- Кубы вращаются только по одной оси, что означает, что поворот [22.5, 0, 0] допустим, а поворот [22.5, 0, 45] не будет работать полностью и повернется только по одной оси.

#### **Кости:**

Кости — это то, что Blockbench называет "группами". Они служат для группировки кубов и должны использоваться для группировки костей для анимаций.

- Кости могут иметь размер до 112x112x112 "пикселей" (единиц Blockbench) или 7x7x7 блоков в игре. *Обратите внимание, что размер костей определяется тем, что они содержат, поэтому если у вас есть кубы, расположенные на расстоянии более 7 блоков друг от друга, вы, вероятно, превысите этот лимит размера. Обойти это ограничение так же просто, как поместить блоки в другую кость, не содержащуюся в первой кости!*
- Могут иметь любое вращение! Однако рекомендуется избегать использования стандартных поворотов 90, -90, 180 и -180, так как они часто могут приводить к неожиданному поведению. Обратите внимание, что это не относится к анимациям, только к стандартному положению покоя костей.

Кости значительно более гибкие, чем кубы, но следует использовать как можно меньше костей! В FMM, из-за ограничений Minecraft, каждая кость является отдельной сущностью. В масштабе это довольно быстро повлияет на производительность! Всегда используйте как можно меньше костей и учитывайте, сколько таких моделей вы планируете заспавнить — чем больше их планируется, тем меньше костей должно быть!

#### **Виртуальные кости**

Виртуальные кости — это терминология ModelEngine для костей, имеющих определенные метаданные, обычно в виде специфического имени, которое используется для конкретной цели.

В FreeMinecraftModels реализованы следующие виртуальные кости:

- Хитбоксы / высота глаз: кость с именем "hitbox" и кубом, который определяет границы, и имеющая одинаковые значения X и Z (будет выбрано наибольшее значение, если они не совпадают), определяет хитбокс. Уровень глаз устанавливается в точке опоры кости хитбокса.
- Именная бирка: кость, имя которой начинается с "tag_". Честно говоря, я бы предпочел быть более конкретным и использовать "tag_name", чтобы использовать теги для других целей, но это будет серьезно рассмотрено позже.
- Голова: кость, имя которой начинается с h_ . Это виртуальная кость, которая используется для определения головы модели, которая будет вращаться в зависимости от вращения головы базовой сущности.

#### **Более безопасное, простое, нередактируемое распространение файлов**

Одна из проблем, которую FMM пытается решить, — это повторное использование пользователями полученных моделей для их редактирования способами, которые не хотел создатель модели, в частности, для изменения текстур или иного незначительного изменения модели и потенциальной попытки перепродать ее как оригинальное творение.

С этой целью FMM использует формат файла `.fmmodel`, который предназначен для урезания файлов `.bbmodel` до такой степени, чтобы они могли использоваться плагином, но не могли быть отредактированы в Blockbench.

Как моделлеру, у вас теперь есть выбор, хотите ли вы выпустить нередактируемый файл `.fmmodel`, редактируемый файл `.bbmodel` или даже установить дифференцированные цены или условия распространения для обоих.

Генерация файла `.fmmodel` так же проста, как помещение вашего файла `.bbmodel` в папку `~/plugins/FreeMinecraftModels/imports` и перезагрузка плагина командой `/fmm reload` или перезапуск сервера. Ваш файл `.fmmodel` затем окажется в папке `~/plugins/FreeMinecraftModels/models`.

## Что FreeMinecraftModels (FMM) может сделать для разработчиков, которые хотят интегрировать его в свои плагины?

У FMM есть репозиторий Maven!
Maven:

```xml
<repository>
    <id>magmaguy-repo-releases</id>
    <name>Репозиторий MagmaGuy</name>
    <url>https://repo.magmaguy.com/releases</url>
</repository>

<dependency>
<groupId>com.magmaguy</groupId>
<artifactId>FreeMinecraftModels</artifactId>
<version>ПОСЛЕДНЯЯ.ВЕРСИЯ.ЗДЕСЬ</version>
</dependency>
```

Gradle:

```kotlin
maven {
    name = "magmaguyRepoReleases"
    url = uri("https://repo.magmaguy.com/releases")
}

compileOnly group : 'com.magmaguy', name: 'FreeMinecraftModels', version: 'ПОСЛЕДНЯЯ.ВЕРСИЯ.ЗДЕСЬ'
```

*Примечание: FreeMinecraftModels предназначен для использования в качестве API и потребует установки плагина на сервере. Не включайте его в свой плагин!*

## Использование API

FMM стремится быть максимально простым в использовании в качестве API.

На данный момент, если вы хотите использовать FreeMinecraftModels в качестве API для доступа к пользовательским моделям, вам нужно знать только о четырех классах:

- `ModeledEntity` - базовый класс для всех сущностей
- `StaticEntity` - для случаев, когда вы хотите использовать непостоянную статическую модель
- `DynamicEntity` - для случаев, когда вы хотите замаскировать другую живую сущность моделью
- `PropEntity` - для случаев, когда вы хотите разместить модель в мире, которая сохраняется даже после перезапуска сервера

Вот фрагмент кода для работы со статической моделью:

```java
import org.bukkit.Bukkit;

public class FreeMinecraftModelsModel {
    private StaticEntity staticEntity = null;

    // Создать модель
    public FreeMinecraftModelsModel(String id, Location location) {
        // Это спавнит сущность!
        staticEntity = StaticEntity.create(id, location);
        // Это проверяет, правильно ли заспавнилась сущность
        if (staticEntity == null) Bukkit.getLogger().warning(("FMM failed to find a model named " + id + " !"));
    }

    public void remove() {
        // Это удаляет сущность
        staticEntity.remove();
    }
}
```

Имейте в виду, что статические модели предназначены для того, чтобы оставаться на месте и служить декоративным элементом в фиксированном местоположении (анимации здесь не считаются 'движением'). Хотя их можно перемещать, подумайте, не лучше ли использовать динамическую модель, если это ваша цель.

А вот как EliteMobs, мой плагин для пользовательских боссов, использует динамические сущности:

```java
package com.magmaguy.elitemobs.thirdparty.custommodels.freeminecraftmodels;

import com.magmaguy.elitemobs.thirdparty.custommodels.CustomModelInterface;
import api.com.magmaguy.freeminecraftmodels.ModeledEntityManager;
import customentity.com.magmaguy.freeminecraftmodels.DynamicEntity;
import lombok.Getter;
import org.bukkit.entity.LivingEntity;

public class CustomModelFMM implements CustomModelInterface {
    @Getter
    private DynamicEntity dynamicEntity;

    public CustomModelFMM(LivingEntity livingEntity, String modelName, String nametagName) {
        dynamicEntity = DynamicEntity.create(modelName, livingEntity);
        if (dynamicEntity == null) return;
        dynamicEntity.setName(nametagName);
    }

    public static void reloadModels() {
        ModeledEntityManager.reload();
    }

    public static boolean modelExists(String modelName) {
        return ModeledEntityManager.modelExists(modelName);
    }

    @Override
    public void shoot() {
        if (dynamicEntity.hasAnimation("attack_ranged")) dynamicEntity.playAnimation("attack_ranged", false);
        else dynamicEntity.playAnimation("attack", false);
    }

    @Override
    public void melee() {
        if (dynamicEntity.hasAnimation("attack_melee")) dynamicEntity.playAnimation("attack_melee", false);
        else dynamicEntity.playAnimation("attack", false);
    }

    @Override
    public void playAnimationByName(String animationName) {
        dynamicEntity.playAnimation(animationName, false);
    }

    @Override
    public void setName(String nametagName, boolean visible) {
        dynamicEntity.setName(nametagName);
        dynamicEntity.setNameVisible(visible);
    }

    @Override
    public void setNameVisible(boolean visible) {
        dynamicEntity.setNameVisible(visible);
    }

    @Override
    public void switchPhase() {
        dynamicEntity.stopCurrentAnimations();
    }
}
```

Динамические модели строятся поверх живой сущности, которая может быть предоставлена либо при использовании метода create, как в примере выше, либо при вызове метода spawn на объекте Dynamic entity.

# Вклад в проект FreeMinecraftModels (FMM) в качестве разработчика

FMM распространяется под лицензией GPLV3, и вклад в код приветствуется. Вот основные правила внесения вклада:

- Следуйте существующим соглашениям об именовании, поддерживайте существующий уровень детализации и добавляйте достаточно документации, чтобы ваш вклад был легко понятен
- Держите вклад в рамках области действия плагина. Если вы не уверены, будет ли он актуален, не стесняйтесь спросить заранее.
- Учитывайте влияние вашего кода на производительность. Некоторые вклады могут быть отклонены, если они слишком неоптимизированы или иным образом вызывают слишком большое влияние на производительность.

## Общее описание плагина

Чтобы сэкономить ваше время, вот краткое описание логики работы FMM:

1) Чтение папки `imports`
2) Перемещение файлов из папки `imports` в папку `models`. Если файл имеет расширение `.bbmodel`, он преобразуется в `.fmmodel` в папке `models`.
3) Чтение файлов в папке `models`.
4) Интерпретация всех структур моделей, создание `Skeleton`ов, которые содержат группы `Bone`ов, а эти кости содержат группы дочерних `Bone`ов и `Cube`ов. `Cube`ы и `Bone`ы генерируют данные JSON ресурс-пака, с которыми они связаны. Это означает, что `Cube`ы генерируют JSON, специфичный для кубов, а `Bone`ы генерируют структуру и файлы отдельных костей. Обратите внимание, что одна кость приводит к одному файлу ресурс-пака. Модели добавляются в список по мере их генерации.
5) Все еще в `Skeleton`, интерпретация всех `Animations` в модели, если таковые имеются
6) Все данные инициализированы, ресурс-пак сгенерирован в папке `outputs`, и плагин готов к использованию.

## Приемы, используемые в этом плагине:

Используемые здесь приемы достаточно хорошо известны и стандартизированы, но тем не менее будут перечислены, поскольку они могут быть неочевидными.

Обратите внимание, что все эти приемы полностью невидимы для пользователей и создателей моделей; ограничения и обходные пути перечислены только для того, чтобы помочь вам понять, как FMM обходит различные ограничения Minecraft.

- Все модели масштабируются в 4 раза, а затем размер и точка опоры корректируются в коде, чтобы расширить теоретический максимальный размер модели
- Поскольку модели ресурс-паков могут иметь размер только от -16 до +32, модели сдвигаются в фоновом режиме. Это полностью невидимо для игроков.
- Кожаная конская броня используется для создания моделей с оттенком, на который можно влиять через код (например, для индикации урона). Конская броня должна быть белой, чтобы отображать правильные цвета!
- Blockbench использует специфическую систему ID для текстур, но на самом деле читает текстуры последовательно из конфигурации. ID здесь присваиваются на основе их позиции в списке текстур, следуя тому, как это делает Blockbench.
- Каждая кость является отдельной сущностью из-за ограничений Minecraft
- Кожаная конская броня находится в слоте головы стойки для брони
- Как стойки для брони, так и сущности отображения используются для статических элементов по умолчанию; клиенты Bedrock получают стойки для брони, а клиенты 1.19.4+ получают сущности отображения (старые клиенты будут получать стойки для брони)

# Вклад в проект FreeMinecraftModels (FMM) в целом

FMM фактически финансируется за счет краудфандинга замечательными людьми на https://www.patreon.com/magmaguy ! Любой вклад помогает больше, чем вы можете себе представить ;)

# Планируемые функции:
- Генерация RSP для клиентов Bedrock
- Управление RSP с интеграцией Geyser
- tag_projectile как мета-кости, из которых могут выстреливаться снаряды (может быть более одной на модель)

# Текущие странные ограничения, которые было бы неплохо исправить:

- TransformationMatrix — это беспорядок, но лучших решений пока не разработано. Требуется работа кого-то, кто хорошо разбирается в матрицах.