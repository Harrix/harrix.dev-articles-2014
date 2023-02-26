---
date: 2014-12-21
categories: [it, program]
tags: [Установка, Java, Android]
update: 2020-08-19
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/install-jdk-8-on-windows/install-jdk-8-on-windows.md
permalink: https://harrix.dev/ru/blog/2014/install-jdk-8-on-windows/
lang: ru
---

# Установка JDK 8 в Windows

![Featured image](featured-image.svg)

Для программирования под Java и, в частности, при создании приложений под Android на компе требуется установка JDK (Java Development Kit). В статье рассказывается как это сделать.

В статье рассматривается способ установки под Widows 10, но никакой разницы для других версий Windows не должно быть. Если вам нужна последняя версия JDK, то посмотрите эту [статью](https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-jdk-on-windows/install-jdk-on-windows.md) <!-- https://harrix.dev/ru/blog/2019/install-jdk-on-windows/ -->.

Скачиваем и устанавливаем с официального сайта:

<http://www.oracle.com/technetwork/java/javase/downloads/index.html>

Сейчас на сайте уже есть Java 14 (на 08.2020). Но для Qt и других программ, использующих Java, по-прежнему рекомендую скачивать **Java 8** (в Android Studio уже можно использовать [Java 14](https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-jdk-on-windows/install-jdk-on-windows.md) <!-- https://harrix.dev/ru/blog/2019/install-jdk-on-windows/ -->):

![Прокрутка окна ниже](img/download_01.png)

_Рисунок 1 — Прокрутка окна ниже_

![Выбор JDK](img/download_02.png)

_Рисунок 2 — Выбор JDK_

![Прокрутка окна ниже](img/download_03.png)

_Рисунок 3 — Прокрутка окна ниже_

![Выбор JDK](img/download_04.png)

_Рисунок 4 — Выбор JDK_

![Соглашение с условиями и скачивание](img/download_05.png)

_Рисунок 5 — Соглашение с условиями и скачивание_

Если у вас 32-битная операционная система, то скачивайте пакет под Windows x86. Для тех, кто не знает: версии программ для 64-битных операционных систем обозначаются **x64**, а для 32-битных обозначаются **x86**. Версии программ x86 можно устанавливать на 64-битные операционные системы, но лучше (за рядом некоторых исключений) устанавливать x64 версии. А версии программ x64 не получится установить на 32-битные операционные системы.

Для скачивания старых версий JDK требуется учетная запись на Oracle:

![Вход в учетную запись Oracle](img/download_06.png)

_Рисунок 6 — Вход в учетную запись Oracle_

Процесс установки обычный и не представляет никаких трудностей:

![Установка](img/install_01.png)

_Рисунок 7 — Установка_

![Установка](img/install_02.png)

_Рисунок 8 — Установка_

![Процесс установки](img/install_03.png)

_Рисунок 9 — Процесс установки_

![Установка JRE](img/install_04.png)

_Рисунок 10 — Установка JRE_

![Процесс установки](img/install_05.png)

_Рисунок 11 — Процесс установки_

![Окончание установки](img/install_06.png)

_Рисунок 12 — Окончание установки_
