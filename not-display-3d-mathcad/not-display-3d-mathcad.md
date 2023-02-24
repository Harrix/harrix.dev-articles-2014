---
date: 2014-04-17
categories: [it, program]
tags: [Mathcad, Математика]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/not-display-3d-mathcad/not-display-3d-mathcad.md
---

# Не отображаются 3D графики MathCAD

В статье показано решение для некоторых компьютеров отображения графиков 3D в Windows 7 и выше.

## Первый способ

Многие столкнулись с переходом на Windows Vista и Windows 7 с проблемой, что 3D графики не отображаются во всех версиях MathCAD, и вместо них видно белый лист. Иногда при поворачивании графика что-то проглядывается, но быстро пропадает.

Проблему можно решить следующим образом.

Двойным кликом по графику открываем меню графика:

![Белый лист вместо графика](img/mathcad_01.png)

Снимаем галочку напротив `Show Border` во вкладке `General` и жмем `OK`:

![Настройки графика](img/mathcad_02.png)

![Снятие галочки у параметра Show Border](img/mathcad_03.png)

График должен появиться:

![Трехмерный график появился](img/mathcad_04.png)

Работает не на всех машинах. Вроде бы только на тех, где стоит Nvidia.

## Второй способ

Надо включить упрощенный стиль Windows 7. Для этого идем `Пуск` → `Панель управления` → `Экран` → `Изменение цветовой схемы` → `Windows 7 - упрощенный стиль`:

![Установка упрощенного стиля в Windows](img/windows.png)

Графики должны появиться. Этот способ подсказал пользователь Ferrum.

## Дополнительно

В новых версиях Mathcad 15 (например, **PTC Mathcad V15 M050**) этот баг исправлен:

![Трехмерные графики](img/mathcad_05.png)
