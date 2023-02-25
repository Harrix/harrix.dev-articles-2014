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
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/install-eclipse-java/install-eclipse-java.md
url: https://harrix.dev/ru/blog/2014/install-eclipse-java/
lang: ru
---

# Установка Eclipse в Windows

В статье рассказывается, как установить Eclipse.

## Установка JDK

Вначале необходимо установить **JDK**. Всё просто, но если есть вопросы, то подробно можно узнать в статье: [Установка JDK в Windows](https://github.com/Harrix/harrix.dev-blog-2019/blob/main/install-jdk-on-windows/install-jdk-on-windows.md).

## Скачивание Eclipse

Идем на сайт: <http://www.eclipse.org/downloads/packages/>.

Скачиваем там последнюю версию Eclipse. Выбираем `Eclipse IDE for Java Developers` версию:

![Ссылка на скачивание установщика](img/download_01.png)

![Выбор версии Eclipse IDE for Java Developers](img/download_02.png)

## Установка Eclipse

Установки так таковой нет. Нужно распаковать скаченный архив куда-нибудь. Например, я распаковал в папку `C:\Android\eclipse`:

![Папка с разархивированным архивом ](img/install.png)

Запускаем файл `eclipse.exe`:

![Первоначальное окно при запуске](img/start-program.png)

## Первоначальная настройка Eclipse

Попросит при старте создать или выбрать `workspace` (папка, где будут храниться ваши проекты):

![Выбор workspace](img/config_01.png)

Рекомендую всегда сразу закрывать окно приветствия, так как в свое время долго не мог понять, почему при создании и открытии проектов проекты не открываются (проекты открывались, только окно приветствия всё загораживало):

![Окно приветствия надо закрыть](img/config_02.png)

Откроется стандартный вид Eclipse:

![Редактор Eclipse](img/eclipse.png)

## Создание нового приложения

![Создание нового проекта](img/new-project_01.png)

Выбираем название нашего проекта:

![Выбор названия проекта](img/new-project_02.png)

Создалась болванка Java проекта. Но в нем нет никаких файлов исходного кода программы. Создадим файл для главного класса приложения:

![Создание нового класса](img/new-project_03.png)

Выбираем название нашего класса (с большой буквы) и ставим галочку около `public static void main(String[] args)`. Эта галочка добавит метод main в наш класс, который нужен для запуска консольного приложения. Фактически это точка входа в приложение:

![Выбор названия класса и его параметров](img/new-project_04.png)

Наш класс создался:

![Выбор названия класса и его параметров](img/new-project_05.png)

## Запуск приложения

В методе `main` пропишем простейшую команду:

```java
System.out.println("Hello, World!");
```

![Строчка Java кода в методе Main](img/java.png)

Запустим проект:

![Запуск приложения](img/run_01.png)

Подтвердим сохранения изменений в файле:

![Запуск приложения](img/run_02.png)

В консоли отобразился результат выполнения программы:

![Запуск приложения](img/run_03.png)
