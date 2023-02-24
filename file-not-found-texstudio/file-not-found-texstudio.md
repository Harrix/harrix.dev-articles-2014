---
date: 2014-12-14
categories: [it, tex]
tags: [LaTeX]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
---

# Ошибка при загрузке пакетов в TeXstudio

В статье рассказывается, как в TeXstudio (точнее проблема вызывается в MiKTeX) решить проблему с отсутствием загрузки пакетов типа: `` File `cmap.sty' not found ``. Вместо пакета `cmap.sty` у вас может быть ошибка с другим пакетом.

Столкнулся с проблемой, когда недавно купил новый ноут с Windows 8.1, и там надо было восстановить всю инфраструктуру, что была на предыдущем ноуте. В том числе надо было [восстановить](https://github.com/Harrix/harrix.dev-blog-2018/blob/main/install-latex/install-latex.md) связку MiKTeX + TeXstudio. Но при попытке первой компиляции файлов с использованием различных пакетов, столкнулся с тем, что MiKTeX не подгружает пакеты, хотя и должен:

![File not found](img/file-not-found_01.png)

Когда пытаемся скомпилировать файл в TeXstudio, то выдается такое окошко, что пакетов не хватает:

![Package Installation](img/package-installation.png)

## Вариант 1

Нажимаем на `Change`:

![Кнопка Change](img/change.png)

Выбираем подключение по интернету:

![Installation Source](img/installation-source_01.png)

И выбираем сервер с стандартными пакетами. Я выбрал первый. Если он вдруг не будет работать, то выберете потом другой:

![Выбор сервера](img/installation-source_02.png)

При таких настройках загрузка пакетов происходит успешно. Напоминаю, что загрузка пакетов может занимать какое-то время.

## Вариант 2

Например, в этом варианте отсутствует пакет `T2` (прислал один из пользователей):

![File not found](img/file-not-found_02.png)

Установим пакет принудительно.

Через пуск находим `MikTex Console`:

![MikTex Console](img/miktex-console_01.png)

И перезапускаем его под администратором:

![MikTex Console](img/miktex-console_02.png)

В разделе `Packages` находим нужный пакет, щелкаем по нему правой кнопкой и устанавливаем его:

![MikTex Console](img/miktex-console_03.png)

Пытаетесь перекомпилировать ваш документ. Если еще какие-то пакеты попросит, то тоже их установите аналогичным способом.