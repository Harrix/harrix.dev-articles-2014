---
date: 2014-04-17
categories:
  - it
  - program
tags:
  - Mathcad
  - Математика
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2014/blob/main/not-display-3d-mathcad/not-display-3d-mathcad.md
permalink: https://harrix.dev/ru/articles/2014/not-display-3d-mathcad/
lang: ru
---

# Не отображаются 3D графики MathCAD

![Featured image](featured-image.svg)

В статье показано решение для некоторых компьютеров отображения графиков 3D в Windows 7 и выше.

<details>
<summary>📖 Содержание ⬇️</summary>

## Содержание

- [Первый способ](#первый-способ)
- [Второй способ](#второй-способ)
- [Дополнительно](#дополнительно)

</details>

## Первый способ

Многие столкнулись с переходом на Windows Vista и Windows 7 с проблемой, что 3D графики не отображаются во всех версиях MathCAD, и вместо них видно белый лист. Иногда при поворачивании графика что-то проглядывается, но быстро пропадает.

Проблему можно решить следующим образом.

Двойным кликом по графику открываем меню графика:

![Белый лист вместо графика](img/mathcad_01.png)

_Рисунок 1 — Белый лист вместо графика_

Снимаем галочку напротив `Show Border` во вкладке `General` и жмем `OK`:

![Настройки графика](img/mathcad_02.png)

_Рисунок 2 — Настройки графика_

![Снятие галочки у параметра Show Border](img/mathcad_03.png)

_Рисунок 3 — Снятие галочки у параметра Show Border_

График должен появиться:

![Трехмерный график появился](img/mathcad_04.png)

_Рисунок 4 — Трехмерный график появился_

Работает не на всех машинах. Вроде бы только на тех, где стоит Nvidia.

## Второй способ

Надо включить упрощенный стиль Windows 7. Для этого идем `Пуск` → `Панель управления` → `Экран` → `Изменение цветовой схемы` → `Windows 7 - упрощенный стиль`:

![Установка упрощенного стиля в Windows](img/windows.png)

_Рисунок 5 — Установка упрощенного стиля в Windows_

Графики должны появиться. Этот способ подсказал пользователь Ferrum.

## Дополнительно

В новых версиях Mathcad 15 (например, **PTC Mathcad V15 M050**) этот баг исправлен:

![Трехмерные графики](img/mathcad_05.png)

_Рисунок 6 — Трехмерные графики_
