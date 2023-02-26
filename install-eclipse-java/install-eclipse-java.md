---
date: 2014-12-22
categories: [it, program]
tags: [Установка, Eclipse, Java]
related-id: start-java
update: 2018
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/install-eclipse-java/install-eclipse-java.md
permalink: https://harrix.dev/ru/blog/2014/install-eclipse-java/
lang: ru
attribution:
  - author: Eclipse Foundation
    author-site: http://www.eclipse.org/
    license: Public domain
    license-url: https://en.wikipedia.org/wiki/Public_domain
    permalink: https://commons.wikimedia.org/wiki/File:Eclipse-Luna-Logo.svg
    permalink-date: 2019-06-07
    name: Eclipse-Luna-Logo.svg
---

# Установка Eclipse в Windows

![Featured image](featured-image.svg)

В статье рассказывается, как установить Eclipse.

## Установка JDK

Вначале необходимо установить **JDK**. Всё просто, но если есть вопросы, то подробно можно узнать в статье: [Установка JDK в Windows](https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-jdk-on-windows/install-jdk-on-windows.md) <!-- https://harrix.dev/ru/blog/2019/install-jdk-on-windows/ -->.

## Скачивание Eclipse

Идем на сайт: <http://www.eclipse.org/downloads/packages/>.

Скачиваем там последнюю версию Eclipse. Выбираем `Eclipse IDE for Java Developers` версию:

![Ссылка на скачивание установщика](img/download_01.png)

_Рисунок 1 — Ссылка на скачивание установщика_

![Выбор версии Eclipse IDE for Java Developers](img/download_02.png)

_Рисунок 2 — Выбор версии Eclipse IDE for Java Developers_

## Установка Eclipse

Установки так таковой нет. Нужно распаковать скаченный архив куда-нибудь. Например, я распаковал в папку `C:\Android\eclipse`:

![Папка с разархивированным архивом ](img/install.png)

_Рисунок 3 — Папка с разархивированным архивом _

Запускаем файл `eclipse.exe`:

![Первоначальное окно при запуске](img/start-program.png)

_Рисунок 4 — Первоначальное окно при запуске_

## Первоначальная настройка Eclipse

Попросит при старте создать или выбрать `workspace` (папка, где будут храниться ваши проекты):

![Выбор workspace](img/config_01.png)

_Рисунок 5 — Выбор workspace_

Рекомендую всегда сразу закрывать окно приветствия, так как в свое время долго не мог понять, почему при создании и открытии проектов проекты не открываются (проекты открывались, только окно приветствия всё загораживало):

![Окно приветствия надо закрыть](img/config_02.png)

_Рисунок 6 — Окно приветствия надо закрыть_

Откроется стандартный вид Eclipse:

![Редактор Eclipse](img/eclipse.png)

_Рисунок 7 — Редактор Eclipse_

## Создание нового приложения

![Создание нового проекта](img/new-project_01.png)

_Рисунок 8 — Создание нового проекта_

Выбираем название нашего проекта:

![Выбор названия проекта](img/new-project_02.png)

_Рисунок 9 — Выбор названия проекта_

Создалась болванка Java проекта. Но в нем нет никаких файлов исходного кода программы. Создадим файл для главного класса приложения:

![Создание нового класса](img/new-project_03.png)

_Рисунок 10 — Создание нового класса_

Выбираем название нашего класса (с большой буквы) и ставим галочку около `public static void main(String[] args)`. Эта галочка добавит метод main в наш класс, который нужен для запуска консольного приложения. Фактически это точка входа в приложение:

![Выбор названия класса и его параметров](img/new-project_04.png)

_Рисунок 11 — Выбор названия класса и его параметров_

Наш класс создался:

![Выбор названия класса и его параметров](img/new-project_05.png)

_Рисунок 12 — Выбор названия класса и его параметров_

## Запуск приложения

В методе `main` пропишем простейшую команду:

```java
System.out.println("Hello, World!");
```

![Строчка Java кода в методе Main](img/java.png)

_Рисунок 13 — Строчка Java кода в методе Main_

Запустим проект:

![Запуск приложения](img/run_01.png)

_Рисунок 14 — Запуск приложения_

Подтвердим сохранения изменений в файле:

![Запуск приложения](img/run_02.png)

_Рисунок 15 — Запуск приложения_

В консоли отобразился результат выполнения программы:

![Запуск приложения](img/run_03.png)

_Рисунок 16 — Запуск приложения_
