---
date: 2014-12-14
categories: [it, hardware]
tags: [Dell, Ноутбук]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/boot-menu-dell-inspiron-5547/boot-menu-dell-inspiron-5547.md
url: https://harrix.dev/ru/blog/2014/boot-menu-dell-inspiron-5547/
lang: ru
---

# Boot menu в Dell Inspiron 5547

![Featured image](featured-image.svg)

В статье рассказано, как загрузить в Dell Inspiron 5547 boot menu для загрузки загрузочного диска.

Купил ноут недавно Dell Inspiron 5547, и сразу поменял на нем винт на гибридный. Соответственно, возникла задача установить операционку. Делал через обычный загрузочный диск через внешний дисковод:

![Ноутбук и внешний дисковод](img/dell-inspiron_01.jpg)

При голом винте, BIOS автоматом находит диск. Но я с разными операционками побаловался (Windows 10 не пошла, так как драйвера на Wi-Fi не поставились). В общем, если на винте есть операционка, то нужно вызывать boot menu.

Для этого при запуске ноута, нажимаем на `F2`:

![Окно ноутбука при его запуске](img/dell-inspiron_02.jpg)

Потом идем в раздел `Boot` стрелочками:

![БИОС ноутбука](img/dell-inspiron_03.jpg)

И там выбираем `Legacy Boot` и нажимаем `Enter`:

![Раздел Boot в БИОС](img/dell-inspiron_04.jpg)

А там выбираем то устройство, с которого хотим произвести запуск, и нажимаем `Enter`.
