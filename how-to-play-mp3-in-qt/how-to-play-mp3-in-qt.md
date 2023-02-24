---
date: 2014-05-08
categories: [it, programming]
tags: [Qt, MP3, C++, Работа с файлами]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/how-to-play-mp3-in-qt/how-to-play-mp3-in-qt.md
---

# Как проиграть MP3 файл в Qt

Небольшая инструкция о том, как проиграть MP3 файл в Qt.

В файле проекта `.pro` прописываем в строчке `QT+` слово `multimedia`. Получаем вот это, например:

```cpp
QT       += core gui multimedia
```

Теперь уже в файле исходнике (например, в `mainwindow.cpp`) подключаем библиотеки:

```cpp
#include <QMediaPlayer>
#include <QDir>
#include <QUrl>
```

И там, где нужно (например, в кнопке), прописываем:

```cpp
QMediaPlayer *player = new QMediaPlayer;
player->setMedia(QUrl::fromLocalFile(QDir::toNativeSeparators("C:\\1.mp3")));
player->setVolume(50);
player->play();
```

Разумеется, что имя файла вы любое можете прописать, также, как и громкость. И разумеется, что сам MP3 файл должен быть на месте.
