---
date: 2014-12-14
categories: [it, tex]
tags: [LaTeX]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/file-not-found-texstudio/file-not-found-texstudio.md
url: https://harrix.dev/ru/blog/2014/file-not-found-texstudio/
lang: ru
---

# Ошибка при загрузке пакетов в TeXstudio

![Featured image](featured-image.svg)

В статье рассказывается, как в TeXstudio (точнее проблема вызывается в MiKTeX) решить проблему с отсутствием загрузки пакетов типа: `` File `cmap.sty' not found ``. Вместо пакета `cmap.sty` у вас может быть ошибка с другим пакетом.

Столкнулся с проблемой, когда недавно купил новый ноут с Windows 8.1, и там надо было восстановить всю инфраструктуру, что была на предыдущем ноуте. В том числе надо было [восстановить](https://github.com/Harrix/harrix.dev-blog-2018/blob/main/install-latex/install-latex.md) <!-- https://harrix.dev/ru/blog/2018/install-latex/ --> связку MiKTeX + TeXstudio. Но при попытке первой компиляции файлов с использованием различных пакетов, столкнулся с тем, что MiKTeX не подгружает пакеты, хотя и должен:

![File not found](img/file-not-found_01.png)

_Рисунок 1 — File not found_

Когда пытаемся скомпилировать файл в TeXstudio, то выдается такое окошко, что пакетов не хватает:

![Package Installation](img/package-installation.png)

_Рисунок 2 — Package Installation_

## Вариант 1

Нажимаем на `Change`:

![Кнопка Change](img/change.png)

_Рисунок 3 — Кнопка Change_

Выбираем подключение по интернету:

![Installation Source](img/installation-source_01.png)

_Рисунок 4 — Installation Source_

И выбираем сервер с стандартными пакетами. Я выбрал первый. Если он вдруг не будет работать, то выберете потом другой:

![Выбор сервера](img/installation-source_02.png)

_Рисунок 5 — Выбор сервера_

При таких настройках загрузка пакетов происходит успешно. Напоминаю, что загрузка пакетов может занимать какое-то время.

## Вариант 2

Например, в этом варианте отсутствует пакет `T2` (прислал один из пользователей):

![File not found](img/file-not-found_02.png)

_Рисунок 6 — File not found_

Установим пакет принудительно.

Через пуск находим `MikTex Console`:

![MikTex Console](img/miktex-console_01.png)

_Рисунок 7 — MikTex Console_

И перезапускаем его под администратором:

![MikTex Console](img/miktex-console_02.png)

_Рисунок 8 — MikTex Console_

В разделе `Packages` находим нужный пакет, щелкаем по нему правой кнопкой и устанавливаем его:

![MikTex Console](img/miktex-console_03.png)

_Рисунок 9 — MikTex Console_

Пытаетесь перекомпилировать ваш документ. Если еще какие-то пакеты попросит, то тоже их установите аналогичным способом.
