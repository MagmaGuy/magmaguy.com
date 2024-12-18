Начиная с версии EliteMobs 7.3.12, в EliteMobs добавлены пользовательские модели через [Model Engine](https://mythiccraft.io/index.php?resources/model-engine%E2%80%94ultimate-entity-model-manager-1-16-5-1-20-4.389/) и [FreeMineCraftModels](https://www.spigotmc.org/resources/free-minecraft-models.111660/).

# Предисловие

С точки зрения EliteMobs, система пользовательских моделей очень проста, так как администраторам нужно лишь добавить строку в файл конфигурации NPC или пользовательского босса, указывающую, какую пользовательскую модель использовать. Однако необходимо выполнить правильные шаги с Model Engine и Minecraft, чтобы эта система заработала в полную силу, и это не так просто.

В этом руководстве подробно рассматривается взаимодействие с Model Engine и Minecraft. В нем не рассказывается, как использовать Blockbench для создания пользовательских боссов, и не описывается подробно, как работает Model Engine. Уже существует множество руководств о том, как это сделать в других местах, и если вы хотите узнать больше об этих системах, лучше обратиться непосредственно к их документации.

## FreeMineCraft Models

Если вы хотите узнать, как использовать FMM для работы ваших моделей, вы можете обратиться к [этой]($language$/freeminecraftmodels/info.md) странице вики, чтобы узнать больше.

# Минимальные требования

EliteMobs 7.3.12 или более поздняя версия, Model Engine R2.2.0\* или более поздняя версия, Blockbench\*\*, использование ресурспаков Minecraft.

\* Этот плагин может иметь дополнительные зависимости. Проверьте документацию с их стороны.
\*\* Необходимо для создания и редактирования пользовательских моделей. Не требуется, если вы просто хотите установить контент, не изменяя его.

# Ручная настройка пользовательской модели

Примечание: это руководство предполагает, что у вас уже есть действительная пользовательская модель. Они поставляются в файловых форматах Blockbench (`.bbmodel`).

EliteMobs может использовать пользовательские модели для NPC и пользовательских боссов. Процесс для этого одинаков для обоих, и он выглядит следующим образом:

## Шаг 1. Настройка конфигурации EliteMobs

Перейдите к файлу конфигурации пользовательского босса или NPC, которого вы хотите изменить, и добавьте следующую строку:

```yaml
customModel: modelname
```

Замените `modelname` на имя вашей модели. Имя - это имя файла пользовательской модели, которую вы используете. В качестве примера, файл пользовательской модели тестового босса - `showcase_boss.bbmodel`. Таким образом, параметр конфигурации должен быть следующим:

```yaml
customModel: showcase_boss
```

И это все для EliteMobs! Теперь все становится немного сложнее.

## Шаг 2. Генерация данных Model Engine

[_Примечание: в случае сомнений или проблем обратитесь к вики Model Engine здесь._](https://github.com/Ticxo/Model-Engine-Wiki/wiki/Importing-and-Exporting#importing)

1. Поместите файл вашей пользовательской модели Blockbench (`.bbmodel`) в каталог `(вашСервер)/plugins/ModelEngine/blueprints` .
2. Выполните команду `/meg reload` . Если все сработало правильно, вы должны получить сообщение `[Model Engine] Загружено X моделей` , где `x` - количество зарегистрированных моделей.

## Шаг 3. Создание ресурспака

[**Примечание: теперь есть альтернативный, более простой способ выполнить этот шаг по этой ссылке.**]($language$/elitemobs/custom_models.md&section=step-2.-generating-the-resource-pack) Однако он немного менее гибкий, чем описано здесь.

Это, возможно, самая сложная часть, если вы хотите, чтобы ваш сервер управлял загрузками. **Попробуйте проверить, работает ли система, когда у вас есть ресурспак на вашем клиенте, прежде чем рассматривать возможность его автоматического распространения!**

1. Перейдите в каталог `(вашСервер)/plugins/ModelEngine/resource pack` и создайте ресурспак, используя эти данные, или добавьте папку `assets` туда в папку `assets` вашего ресурспака.
   1. Если вы создаете новый ресурспак, вы можете поместить файлы в `resource pack` в zip-файл, и это будет действительный ресурспак, который вы сможете распространять. [Больше информации](https://github.com/Ticxo/Model-Engine-Wiki/wiki/Importing-and-Exporting#preexisting-resource-pack).
   2. Если у вас уже есть ресурспак, убедитесь, что вы случайно не перезаписываете существующие модели. [Больше информации](https://github.com/Ticxo/Model-Engine-Wiki/wiki/Importing-and-Exporting#preexisting-resource-pack).
2. Распространите свой ресурспак среди своих игроков. **Только игроки, у которых есть ресурспак, смогут видеть пользовательские модели**, и для всех остальных он будет выглядеть очень странно и сломанно. Если вы намереваетесь активно использовать их, возможно, вам захочется принудительно использовать ресурспак.
   1. (Необязательно) Чтобы разрешить игрокам загружать ресурспак при входе в систему, вам нужно разместить файл где-нибудь в Интернете и изменить поле `resource-pack=` в server.properties, чтобы оно указывало на этот адрес.**\***
   2. (Необязательно) Если вы изменяете ресурспаки, вам нужно будет использовать параметр `resource-pack-sha1=`, чтобы сервер мог проверить, нужно ли обновлять ресурспак игрока. Чтобы сгенерировать это значение, загрузите свой ресурспак на [http://onlinemd5.com/](http://onlinemd5.com/) и убедитесь, что вы выбрали опцию SHA1. Вам придется делать это каждый раз, когда вы обновляете свой ресурспак, иначе ваши пользователи не получат обновление.**\***
   3. (Необязательно) Чтобы заставить игроков использовать ресурспаки, используйте опцию `require-resource-pack=true` в server.properties.**\***

**Если вы изменили server.properties, вам нужно будет перезапустить сервер!**

**\*** Примечание: В Интернете есть множество руководств, которые могут помочь вам заставить это работать, если эти инструкции вам не помогают.

### Объединение ресурспаков

Если вам нужно объединить свои ресурспаки, вы можете сделать это вручную. Но мы рекомендуем использовать онлайн-инструмент, такой как [merge.elmakers](https://merge.elmakers.com/), для объединения ваших ресурспаков.

## Шаг 4. Надежда, что это сработает

Если все было сделано правильно, теперь вы должны увидеть пользовательскую модель на своем боссе или NPC. Вы можете создать их с помощью команд:

* Пользовательский босс: `/em spawncustom имя_файла.yml`
* NPC: `/em spawnnpc имя_файла.yml`

Затем вы можете удалить их с помощью команды `/em remove`.

# Создание и адаптация пользовательских моделей для EliteMobs

EliteMobs может использовать любую модель, считающуюся действительной Model Engine, а это означает, что с ее помощью можно сделать практически все.

Однако, когда дело доходит до анимации, использование определенных имен для анимации требуется для гарантии того, что боссы смогут использовать анимацию.

Эти имена анимации - это те, которые установлены в Blockbench на вкладке "Анимации". Вы можете переименовать их в любое время, что означает, что вы можете модернизировать любые существующие модели для работы с EliteMobs.

## Анимация

Обратите внимание, что этот раздел все еще расширяется, так как эта система совсем новая. По мере поступления запросов на добавление функций в него будет добавлено больше.

### idle

`idle` - это правильное имя анимации для сущностей, которые не находятся в бою и не двигаются. EliteMobs не изменяет систему анимации бездействия по умолчанию, используемую Model Engine.

### walk

`walk` - это правильное имя анимации для сущностей, которые движутся. EliteMobs не изменяет систему анимации бездействия по умолчанию, используемую Model Engine.

### attack

Существует три типа анимации атаки:

#### attack

`attack` - это правильное общее имя анимации для случая, когда босс атакует.

#### attack_melee

`attack_melee` - это правильное имя анимации для атак, выполняемых, когда пользовательский босс атакует сущность, используя обычную атаку ближнего боя Minecraft. Переопределяет `attack`. Обратите внимание, что анимация воспроизводится **после** нанесения урона. К сожалению, это ограничение на данный момент. Поэтому старайтесь, чтобы анимация была очень быстрой.

#### attack_ranged

`attack_ranged` - это правильное имя анимации для атак, выполняемых, когда пользовательский босс порождает метательное снаряд. Переопределяет `attack`. Обратите внимание, что анимация воспроизводится **после** выстрела снаряда. К сожалению, это ограничение на данный момент. Поэтому старайтесь, чтобы анимация была очень быстрой.

### damaged

`damaged` - это правильное имя анимации для анимации боли, которую пользовательский босс воспроизводит при получении урона.

### death

`death` - это правильное имя анимации для анимации смерти. EliteMobs не изменяет систему анимации бездействия по умолчанию, используемую Model Engine.

### powers

Примечание: этот сегмент все еще находится в стадии разработки. Ниже приведены функции в том виде, в котором они запланированы.

Каждая способность в EliteMobs может иметь назначенную ей анимацию. Анимация всегда начинается при активации способности, и в настоящее время не предусмотрено дальнейших триггеров во время использования способности. Некоторые способности, такие как неуязвимости, ничего не делают, так как у них нет триггеров и они являются просто пассивными свойствами боссов.

Чтобы назначить анимацию способности, анимация должна иметь то же имя, что и файл способности elitemobs.

В качестве примера, чтобы добавить анимацию к способности зомби некрономикон, анимация должна называться `zombie_necronomicon.yml` . Она начнет воспроизводиться, как только способность будет активирована, и закончится, когда закончится анимация, если она не настроена на циклическое воспроизведение или когда способность будет завершена.

# Импорт пользовательских моделей из подземелий

## Шаг 1. Обычный импорт

При импорте заархивированной папки пакета подземелий, содержащей пользовательские модели, пользовательские модели автоматически перемещаются в `(вашСервер)/plugins/ModelEngine/blueprints`, и Model Engine автоматически перезагружается для создания соответствующих ресурспаков и файлов Model Engine.

## Шаг 2. Создание ресурспака

Если вы находитесь в сети при перезагрузке EliteMobs для импорта файлов, EliteMobs автоматически опубликует в чате сообщение, на которое можно нажать, чтобы сгенерировать ресурспак EliteMobs. В качестве альтернативы вы можете выполнить команду `/em generateresourcepack`, чтобы сгенерировать его.

Выполнение этой команды копирует все файлы ресурспака в папку `exports` EliteMobs неразрушающим способом. Это означает, что если вы разархивируете ресурспак в папку exports, используя имя ресурспака `elitemobs_resource_pack` для вашей папки ресурспака, EliteMobs не удалит ни один из файлов, находящихся в ней, если только файл с таким же именем не будет получен из ModelEngine (за исключением pack.meta и pack.png). Таким образом, вы можете обновить свой ресурспак, не потеряв модели, которые вы ранее в него поместили.

Наконец, EliteMobs архивирует ресурспак в папке `exports`, и этот файл готов к распространению.

После этого EliteMobs также предлагает обновить SHA1-код для вашего ресурспака.

### Шаг 2.5. Обновление SHA1

SHA1-код в файле `server.properties` используется для того, чтобы клиенты знали, устарел ли их ресурспак, и заставляет их обновить его, если это необходимо. Этот код можно сгенерировать через EliteMobs, нажав на опцию в чате, которая появляется после шага 2, или выполнив команду `/em updateresourcepack`

**Имейте в виду, что это обновляет ваш файл server.properties правильным SHA1-кодом для заархивированного ресурспака в папке `exports`.** Если вы удалите его или измените заархивированный файл после выполнения команды, он не будет работать.

## Шаг 3. Сделайте файл общедоступным

Разместите файл в выбранном вами месте. Некоторые люди используют для этого Google Диск или Dropbox. Лучше всего разместить этот файл самостоятельно, если у вас есть такая возможность. Некоторые плагины также могут помочь вам разместить его непосредственно с вашего сервера Minecraft. Если вы найдете такой плагин, который работает, сообщите об этом MagmaGuy в Discord, и этот пост будет обновлен этой информацией.
