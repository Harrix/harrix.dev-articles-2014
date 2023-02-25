---
date: 2014-10-19
categories: [it, program]
tags: [Notepad++, Текстовой редактор]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/remove-duplicate-lines/remove-duplicate-lines.md
url: https://harrix.dev/ru/blog/2014/remove-duplicate-lines/
lang: ru
---

# Удаление дублирующих строк в Notepad++

![Featured image](featured-image.svg)

Надо удалить повторяющиеся строки в текстовом файле. Для этого воспользуемся Notepad++.

Прямой функции в Notepad++ нет, но можно воспользоваться некоторыми функциями, чтобы всё реализовать.

Допустим, что у нас есть файл такого содержания:

```text
abc@mail.ru
owrewt@mail.ru
r6uywru@mail.ru
abc@mail.ru
ryetuetiet@mail.ru
gdefjfsdjfdj@mail.ru
```

## Первый способ

Запустите окно замены в файле и введите команду:

```text
^(.*?)$\s+?^(?=.*^\1$)
```

При этом настройки замены должны быть как на рисунке:

![Настройки замены](img/replace.png)

_Рисунок 1 — Настройки замены_

И нажмите `Заменить всё`. Повторяющиеся строки удаляться. Но при этом останутся не первые варианты строк, а последние повторы.

## Второй способ

Если надо удалить повторы так, чтобы оставалось первые варианты строк, а не последние, то тут надо по-другому поступить. Идея простая. Мы меняем порядок строк, а потом просто применяем первый способ, а потом меняем обратно.

Для этого нам потребуется плагин [TextFX](https://github.com/Harrix/harrix.dev-blog-2013/blob/main/textfx/textfx.md). По ссылке рассказывается и про его установку.

Итак, нужно сделать следующие действия для изменения порядка строк.

Выделите весь текст `Ctrl` + `A`:

![Выделение всего текста](img/select-all.png)

_Рисунок 2 — Выделение всего текста_

Вставьте номера строкам: `TextFX` → `TextFX Tools` → `Insert Line Numbers`:

![Insert Line Numbers](img/insert-line-numbers.png)

_Рисунок 3 — Insert Line Numbers_

Если стоит флажок `TextFX` → `TextFX Tools` → `+Sort ascending`, то его убрать:

![Команда +Sort ascending](img/sort-ascending.png)

_Рисунок 4 — Команда +Sort ascending_

Отсортируем строки `TextFX` → `TextFX Tools` → `Sort lines case sensitive (at column)`:

![Sort lines case sensitive (at column)](img/sort-lines-case-sensitive.png)

_Рисунок 5 — Sort lines case sensitive (at column)_

Удаляем номера строк `TextFX` → `TextFX Tools` → `Delete Line Numbers or First Word`:

![Delete Line Numbers or First Word](img/delete-line-numbers.png)

_Рисунок 6 — Delete Line Numbers or First Word_

Потом используем первый способ для удаление повторяющихся строк. А потом обратно меняем порядок строк.

## Третий способ

Но я бы всё-таки для таких целей использовал бы специализированные средства (ибо, иногда способы в статье немного шалят). Вот два рабочий сервиса, которыми я пользуюсь при случае:

<http://textmechanic.com/Remove-Duplicate-Lines.html>

<http://www.textfixer.com/tools/remove-duplicate-lines.php>
