---
date: 2014-02-02
categories: [it, program]
tags: [Установка, Qt, MinGW]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2014/blob/main/install-qt-on-windows-xp/install-qt-on-windows-xp.md
permalink: https://harrix.dev/ru/articles/2014/install-qt-on-windows-xp/
lang: ru
attribution:
  - {
      author: Qt Project,
      author-site: "https://www.qt.io",
      license: Public domain,
      license-url: "https://en.wikipedia.org/wiki/Public_domain",
      permalink: "https://commons.wikimedia.org/wiki/File:Qt_logo_2016.svg",
      permalink-date: 2019-01-26,
      name: Qt logo 2016.svg,
    }
---

# Установка Qt 4.8.4 на Windows XP

![Featured image](featured-image.svg)

Пригласили меня преподавать Qt в одну школу. Всё бы хорошо, но у них стоит Windows XP и современные версии Qt или старые версии QtSDK не устанавливаются (или вообще не запускают процесс установки или вызывают ошибку). Выкрутился установкой связки Qt 4.8.4 + QtCreator 2.5.2 + MinGW.

- [Файлы](#файлы)
- [Установка](#установка)
- [Настройка](#настройка)

## Файлы

Скачивал я Qt 4.8.4 и QtCreator 2.5.2 отсюда: <http://download.qt.io/archive/>.

Если более конкретно, то Qt 4.8.4 в виде файла `qt-win-opensource-4.8.4-mingw.exe` скачал из этой папки: <http://download.qt.io/archive/qt/4.8/4.8.4/>.

А QtCreator 2.5.2 в виде файла `qt-creator-win-opensource-2.5.2.exe` скачал из этой папки: <http://download.qt.io/archive/qtcreator/2.5/>.

Архив MinGW, который с ними заработал можно взять с этого сайта: [mingw.zip](files/mingw.zip).

## Установка

Распаковываем архив.

Папку `Mingw` копируем в корень диска `C:\`:

![Распаковка архива с MinGW](img/mingw.png)

_Рисунок 1 — Распаковка архива с MinGW_

Запускаем файл `qt-win-opensource-4.8.4-mingw.exe` от имени администратора:

![Запуск от имени администратора](img/install_01.png)

_Рисунок 2 — Запуск от имени администратора_

![Начальное окно установки](img/install_02.png)

_Рисунок 3 — Начальное окно установки_

В месте, где просит показать, где MinGW, показываете, где он:

![Выбор месторасположения MinGW](img/install_03.png)

_Рисунок 4 — Выбор месторасположения MinGW_

![Выбор месторасположения MinGW через Обзор папок](img/install_04.png)

_Рисунок 5 — Выбор месторасположения MinGW через Обзор папок_

Дальше всё по умолчанию:

![Процесс установки](img/install_05.png)

_Рисунок 6 — Процесс установки_

Запускаем файл `qt-creator-win-opensource-2.5.2.exe` от имени администратора:

![Запуск от имени администратора](img/install_06.png)

_Рисунок 7 — Запуск от имени администратора_

Установка не вызывает никаких проблем:

![Начальное окно установки](img/install_07.png)

_Рисунок 8 — Начальное окно установки_

## Настройка

Поменяем язык на английский:

![Параметры Qt](img/config_01.png)

_Рисунок 9 — Параметры Qt_

![Замена языка интерфейса на английский](img/config_02.png)

_Рисунок 10 — Замена языка интерфейса на английский_

Перезапускаем QtCreator.

Опять идем в настройки, но уже по-английски:

![Тот же пункт параметров Qt](img/config_03.png)

_Рисунок 11 — Тот же пункт параметров Qt_

Соединим QtCreator и Qt:

![Добавление папки Qt в QtCreator](img/config_04.png)

_Рисунок 12 — Добавление папки Qt в QtCreator_

Находим папку Qt и выбираем там файл `qmake.exe`. У меня это папка `C:\Qt4.8.4\bin`:

![Папка с файлом qmake.exe](img/config_05.png)

_Рисунок 13 — Папка с файлом qmake.exe_

![Результат добавления папки с Qt](img/config_06.png)

_Рисунок 14 — Результат добавления папки с Qt_

Соединим Qt и MinGW:

![Добавление MinGW](img/config_07.png)

_Рисунок 15 — Добавление MinGW_

Находим папку MinGW и выбираем там файл `mingw32-make.exe`. У меня это папка `C:\Mingw\bin`:

![Добавление пути с файлом mingw32-make.exe](img/config_08.png)

_Рисунок 16 — Добавление пути с файлом mingw32-make.exe_

![Нахождение файла mingw32-make.exe](img/config_09.png)

_Рисунок 17 — Нахождение файла mingw32-make.exe_

![Результат добавления файла mingw32-make.exe](img/config_10.png)

_Рисунок 18 — Результат добавления файла mingw32-make.exe_

Всё! Приложения создаются и компилируются:

![Пример запуска приложения Qt](img/qt.png)

_Рисунок 19 — Пример запуска приложения Qt_
