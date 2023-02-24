---
date: 2014-02-02
categories: [it, program]
tags: [Установка, Qt, MinGW]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
---

# Установка Qt 4.8.4 на Windows XP

Пригласили меня преподавать Qt в одну школу. Всё бы хорошо, но у них стоит Windows XP и современные версии Qt или старые версии QtSDK не устанавливаются (или вообще не запускают процесс установки или вызывают ошибку). Выкрутился установкой связки Qt 4.8.4 + QtCreator 2.5.2 + MinGW.

## Файлы

Скачивал я Qt 4.8.4 и QtCreator 2.5.2 отсюда: <http://download.qt.io/archive/>.

Если более конкретно, то Qt 4.8.4 в виде файла `qt-win-opensource-4.8.4-mingw.exe` скачал из этой папки: <http://download.qt.io/archive/qt/4.8/4.8.4/>.

А QtCreator 2.5.2 в виде файла `qt-creator-win-opensource-2.5.2.exe` скачал из этой папки: <http://download.qt.io/archive/qtcreator/2.5/>.

Архив MinGW, который с ними заработал можно взять с этого сайта: [mingw.zip](files/mingw.zip).

## Установка

Распаковываем архив.

Папку `Mingw` копируем в корень диска `C:\`:

![Распаковка архива с MinGW](img/mingw.png)

Запускаем файл `qt-win-opensource-4.8.4-mingw.exe` от имени администратора:

![Запуск от имени администратора](img/install_01.png)

![Начальное окно установки](img/install_02.png)

В месте, где просит показать, где MinGW, показываете, где он:

![Выбор месторасположения MinGW](img/install_03.png)

![Выбор месторасположения MinGW через Обзор папок](img/install_04.png)

Дальше всё по умолчанию:

![Процесс установки](img/install_05.png)

Запускаем файл `qt-creator-win-opensource-2.5.2.exe` от имени администратора:

![Запуск от имени администратора](img/install_06.png)

Установка не вызывает никаких проблем:

![Начальное окно установки](img/install_07.png)

## Настройка

Поменяем язык на английский:

![Параметры Qt](img/config_01.png)

![Замена языка интерфейса на английский](img/config_02.png)

Перезапускаем QtCreator.

Опять идем в настройки, но уже по-английски:

![Тот же пункт параметров Qt](img/config_03.png)

Соединим QtCreator и Qt:

![Добавление папки Qt в QtCreator](img/config_04.png)

Находим папку Qt и выбираем там файл `qmake.exe`. У меня это папка `C:\Qt4.8.4\bin`:

![Папка с файлом qmake.exe](img/config_05.png)

![Результат добавления папки с Qt](img/config_06.png)

Соединим Qt и MinGW:

![Добавление MinGW](img/config_07.png)

Находим папку MinGW и выбираем там файл `mingw32-make.exe`. У меня это папка `C:\Mingw\bin`:

![Добавление пути с файлом mingw32-make.exe](img/config_08.png)

![Нахождение файла mingw32-make.exe](img/config_09.png)

![Результат добавления файла mingw32-make.exe](img/config_10.png)

Всё! Приложения создаются и компилируются:

![Пример запуска приложения Qt](img/qt.png)
