---
date: 2014-12-16
categories:
  - it
  - program
tags:
  - Notepad++
  - Текстовой редактор
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2014/blob/main/delete-every-second-line/delete-every-second-line.md
permalink: https://harrix.dev/ru/articles/2014/delete-every-second-line/
lang: ru
---

# Как удалить каждую вторую строку в Notepad++

![Featured image](featured-image.svg)

В статье рассказывается как удалить в документе каждую вторую строку в Notepad++.

Допустим у нас такой документ в Notepad++:

![Текст для тестирования](img/text_01.png)

_Рисунок 1 — Текст для тестирования_

Нажимаем `Ctrl` + `F` и переходим в закладку `Заменить`.

Вводим в поле поиска такой текст:

```text
([^\n]*\n)[^\n]*\n
```

В поле заменить вводим:

```text
$1
```

Выставим вот такие параметры замены:

![Параметры замены](img/replace.png)

_Рисунок 2 — Параметры замены_

В итоге получим, что удалены каждая вторая строка:

![Текст с удаленными строками](img/text_02.png)

_Рисунок 3 — Текст с удаленными строками_

Если не сработает код, то в поле текста добавляем вот такой код:

```text
([^\r\n]*[\r\n]+)[^\r\n]*[\r\n]*
```

И повторяем.
