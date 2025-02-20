---
date: 2014-07-17
categories:
  - it
  - photo
tags:
  - Обработка фотографии
  - Adobe Pixel Bender Toolkit
download: https://github.com/Harrix/harrix.dev-articles-2014/raw/main/droste-effect/files/droste.zip
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2014/blob/main/droste-effect/droste-effect.md
permalink: https://harrix.dev/ru/articles/2014/droste-effect/
lang: ru
---

# Как сделать эффект Дросте

![Featured image](featured-image.svg)

Эффект Дросте (нидерл. Droste-effect) — рекурсивное изображение как частный случай техники mise en abîme. То есть это рисунок в рисунке и так далее. В уроке показано как такое можно сделать самому.

Вы видели вот такие картинки в интернете:

![Пример эффекта Дросте](img/example_01.jpg)

_Рисунок 1 — Пример эффекта Дросте_

![Пример эффекта Дросте](img/example_02.jpg)

_Рисунок 2 — Пример эффекта Дросте_

Будем сегодня учиться создавать подобные картинки.

Для начала нам потребуется установить **Adobe Pixel Bender Toolkit 2**. Скачать можно по ссылке <http://www.adobe.com/devnet/pixelbender.html>:

![Скачивание Adobe Pixel Bender Toolkit 2](img/download_01.png)

_Рисунок 3 — Скачивание Adobe Pixel Bender Toolkit 2_

Установка простая и не требует каких-нибудь особых знаний. Теперь нам нужно найти и скачать плагин для этой программы (скорее это скрипт), который и будет трансформировать наши изображения. Идем по ссылке <http://2008.sub.blue/projects/droste.html> и скачиваем. В архиве нам потребуется файл `Droste.pbk`:

![Скачивание скрипта Droste.pbk](img/download_02.png)

_Рисунок 4 — Скачивание скрипта Droste.pbk_

Или можете скачать с этого сайта: [droste.zip](files/droste.zip).

Открываем `Adobe Pixel Bender Toolkit 2`:

![Открытый Adobe Pixel Bender Toolkit 2](img/droste_01.png)

_Рисунок 5 — Открытый Adobe Pixel Bender Toolkit 2_

Справа внизу у нас есть кнопка «Open a filter…». Нажимаем ее и открываем файл `Droste.pbk`. У нас внизу откроется код данного скрипта:

![Код скрипта](img/droste_02.png)

_Рисунок 6 — Код скрипта_

В главном меню загружаем тот рисунок, который вы хотите трансформировать:

![Пункт меню для загрузки изображения](img/droste_03.png)

_Рисунок 7 — Пункт меню для загрузки изображения_

Я решил взять вот такую фотографию:

![Фотография, взятая для примера](img/for-example.jpg)

_Рисунок 8 — Фотография, взятая для примера_

Нажимаем внизу кнопку «Build and Run…». У нас появится первый набросок фотографии, а справа появится панель управления, где вы можете изменять параметры построения картинки:

![Настройки эффекта Droste](img/droste_04.png)

_Рисунок 9 — Настройки эффекта Droste_

![Кнопка построения изображения](img/droste_05.png)

_Рисунок 10 — Кнопка построения изображения_

Сохранить полученный результат можете обычным способом:

![Пункт меню для сохранения фотографии](img/droste_06.png)

_Рисунок 11 — Пункт меню для сохранения фотографии_

Далее всё будет решать ваша фантазия и подкрутка параметров на картинках. Приведу несколько примеров, которые я замутил на скорую руку:

![Пример эффекта Дросте](img/example_03.jpg)

_Рисунок 12 — Пример эффекта Дросте_

![Пример эффекта Дросте](img/example_04.jpg)

_Рисунок 13 — Пример эффекта Дросте_
