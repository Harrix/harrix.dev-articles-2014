---
date: 2014-01-04
categories: [it, program]
tags: [Notepad++, Текстовой редактор, Проверка орфографии]
update: 2020-08-18
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/spell-check-in-notepad/spell-check-in-notepad.md
---

# Проверка орфографии в Notepad++

В статье описывается способ подключения проверки орфографии на русском и английском языках в Notepad++.

В 2020 году плагин `DSpellCheck` не устанавливается по умолчанию, поэтому это нужно сделать самому:

![Управление плагинами](img/plugins_01.png)

![Установка плагина](img/plugins_02.png)

![Включение плагина](img/plugins_03.png)

Перейдите в Notepad++ в настройки плагина `DSpellCheck` по проверке орфографии:

![Выбор настроек плагина](img/spell-check_01.png)

Смотрите, чтобы наверху был выбран пункт `Hunspell`. После перейдите в режим загрузки словарей (английский по умолчанию загружен):

![Настройки плагина](img/spell-check_02.png)

Выделите русские словари и те, что вы хотите. Затем установите словари:

![Выбор словарей](img/spell-check_03.png)

В процессе будут показаны вот такие картинки:

![Установка словарей](img/spell-check_04.png)

![Установка словарей](img/spell-check_05.png)

Теперь включим одновременную проверку нескольких языков:

![Включение проверки нескольких языков](img/spell-check_06.png)

Выберем языки, которые нас интересуют:

![Выбор языков](img/spell-check_07.png)

Теперь всё готово. Нажимайте на `OK`

Проверка орфографии заработала:

![Результат проверки орфографии](img/spell-check_08.png)
