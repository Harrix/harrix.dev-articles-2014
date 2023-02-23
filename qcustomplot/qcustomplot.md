---
date: 2014-05-25
categories: [it, programming]
tags: [Qt, Графики, C++, Chart, Plot]
update: 2018
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
---

# Графики в Qt через QCustomPlot

В статье показывается пример установки и демонстрации возможностей библиотеки QCustomPlot для рисования графиков на QtWidgets.

**Update 2018.** В бесплатной версии Qt появились [Qt Charts](http://doc.qt.io/qt-5/qtcharts-index.html), но они распространяются по GPL лицензии. А это накладывает очень серьезные ограничения для распространения ваших программ. Поэтому для нормального использования Qt Charts нужно брать платную версию Qt.

Поэтому приветствуются альтернативы, которой и является QCustomPlot.

## Где найти

Идем на сайт <https://www.qcustomplot.com>:

![Сайт библиотеки](img/download_01.png)

И скачиваем библиотеку из соответствующего раздела:

![Скачивание библиотеки](img/download_02.png)

Из всей библиотеки нам потребуется только два файла: `qcustomplot.cpp` и `qcustomplot.h`:

![Файлы библиотеки](img/files_01.png)

## Подключение библиотеки

Создадим для примера приложение Qt Widgets:

![Выбор типа проектов](img/new-project.png)

В папку с исходными кодами проекта скинем наши два файла библиотеки. Обратите на этот шаг внимание! Многие данный шаг, как показывает практика, пропускают, и загружают потом в проект эти файлы из распакованного архива, а не из папки своего проекта:

![Папка проекта](img/files_02.png)

Щелкнем правой кнопкой по проекту в Qt Creator и выберем добавление существующих файлов `Add Existing Files…`:

![Add Existing Files…](img/add-existing-files_01.png)

Выберем два наших файла библиотеки:

![Выбор файлов библиотеки](img/add-existing-files_02.png)

Они добавятся к нашему проекту:

![Файлы библиотеки в проекте](img/add-existing-files_03.png)

Перейдем в файл проекта `.pro` и допишем там слово `printsupport`:

![Файл проекта .pro](img/printsupport.png)

Перейдем на форму:

![Форма проекта](img/form.png)

Разместим там кнопку и `Widget`:

![Компоненты на форме](img/widget_01.png)

Щелкнем по `Widget` правой кнопкой и перейдем к `Promote to…`:

![Promote to…](img/widget_02.png)

Там пропишем класс графиков `QCustomPlot` и нажмем на `Add…`:

![Добавление класса библиотеки](img/widget_03.png)

А потом на `Promote`:

![Подключение класса библиотеки к виджету](img/widget_04.png)

Внешне ничего не изменилось, но, если мы запустим приложение, то увидим координатную сетку:

![Запуск приложения](img/run.png)

![Координатная сетка в запущенном приложении](img/application.png)

Иногда после данных действий кнопка запуска неактивна и серая вместо того, чтобы быть зеленой. Данный глюк, можно, например, быстро решить, переключить режим компилирования с Debug на Release (или наоборот), а потом обратно переключить:

![Переключение режимов сборки](img/release-debug.png)

Теперь нарисуем какой-нибудь график. Нам потребуется имя компонента Widget, чтобы обращаться к нему:

![Нахождение имени компонента](img/widget_05.png)

Перейдем к коду кнопки при клике:

![Переход к слоту кнопки](img/go-to-slot.png)

И напишем, например, такой код:

```cpp
//Рисуем график y=x*x
//Сгенерируем данные
//Для этого создадим два массива точек:
//один для сохранения x координат точек,
//а второй для y соответственно
double a = -1; //Начало интервала, где рисуем график по оси Ox
double b =  1; //Конец интервала, где рисуем график по оси Ox
double h = 0.01; //Шаг, с которым будем пробегать по оси Ox
int N = (b - a) / h + 2; //Вычисляем количество точек, которые будем отрисовывать
QVector<double> x(N), y(N); //Массивы координат точек

//Вычисляем наши данные
int i=0;
//Пробегаем по всем точкам
for (double X = a; X <= b; X += h) {
  x[i] = X;
  y[i] = X * X;//Формула нашей функции
  i++;
}
ui->widget->clearGraphs();//Если нужно, но очищаем все графики

//Добавляем один график в widget
ui->widget->addGraph();

//Говорим, что отрисовать нужно график по нашим двум массивам x и y
ui->widget->graph(0)->setData(x, y);

//Подписываем оси Ox и Oy
ui->widget->xAxis->setLabel("x");
ui->widget->yAxis->setLabel("y");

//Установим область, которая будет показываться на графике
ui->widget->xAxis->setRange(a, b);//Для оси Ox

//Для показа границ по оси Oy сложнее, так как надо по правильному
//вычислить минимальное и максимальное значение в векторах
double minY = y[0], maxY = y[0];
for (int i = 1; i < N; i++) {
  if (y[i] < minY) minY = y[i];
  if (y[i] > maxY) maxY = y[i];
}
ui->widget->yAxis->setRange(minY, maxY);//Для оси Oy

//И перерисуем график на нашем widget
ui->widget->replot();
```

При запуске приложение и нажатии на кнопку получим вот это:

![График в приложении](img/result_01.png)

Вот и всё. Много примеров ещё в архиве с данной библиотекой, что вы скачивали, и на сайте ее тоже много. Так что дерзайте!

## График в виде точек

Чтобы график рисовался не линией, а точками, достаточно прописать это в свойствах графика. Ниже представлен пример такого графика:

```cpp
ui->widget->graph(0)->setPen(QColor(50, 50, 50, 255));//задаем цвет точки
ui->widget->graph(0)->setLineStyle(QCPGraph::lsNone);//убираем линии
//формируем вид точек
ui->widget->graph(0)->setScatterStyle(QCPScatterStyle(QCPScatterStyle::ssCircle, 4));
```

Полный код:

```cpp
//Рисуем график точками y=x*x
//Сгенерируем данные
//Для этого создадим два массива точек:
//один для сохранения x координат точек,
//а второй для y соответственно
double a = -1; //Начало интервала, где рисуем график по оси Ox
double b =  1; //Конец интервала, где рисуем график по оси Ox
double h = 0.1; //Шаг, с которым будем пробегать по оси Ox
int N = (b - a) / h + 2; //Вычисляем количество точек, которые будем отрисовывать
QVector<double> x(N), y(N); //Массивы координат точек

//Вычисляем наши данные
int i=0;
//Пробегаем по всем точкам
for (double X = a; X <= b; X += h) {
  x[i] = X;
  y[i] = X * X;//Формула нашей функции
  i++;
}
ui->widget->clearGraphs();//Если нужно, но очищаем все графики

//Добавляем один график в widget
ui->widget->addGraph();

//Говорим, что отрисовать нужно график по нашим двум массивам x и y
ui->widget->graph(0)->setData(x, y);
ui->widget->graph(0)->setPen(QColor(50, 50, 50, 255));//задаем цвет точки
ui->widget->graph(0)->setLineStyle(QCPGraph::lsNone);//убираем линии

//формируем вид точек
ui->widget->graph(0)->setScatterStyle(QCPScatterStyle(QCPScatterStyle::ssCircle, 4));

//Подписываем оси Ox и Oy
ui->widget->xAxis->setLabel("x");
ui->widget->yAxis->setLabel("y");

//Установим область, которая будет показываться на графике
ui->widget->xAxis->setRange(a, b);//Для оси Ox

//Для показа границ по оси Oy сложнее, так как надо по правильному
//вычислить минимальное и максимальное значение в векторах
double minY = y[0], maxY = y[0];
for (int i = 1; i < N; i++) {
  if (y[i] < minY) minY = y[i];
  if (y[i] > maxY) maxY = y[i];
}
ui->widget->yAxis->setRange(minY, maxY);//Для оси Oy

//И перерисуем график на нашем widget
ui->widget->replot();
```

![График в виде точек](img/result_02.png)

## График массива точек

Ниже рассмотрен более простой пример, где отображается график в виде точек из набора точек, заданных вручную:

```cpp
//Рисуем точки
int N = 5; //Допустим, что у нас пять точек
QVector<double> x(N), y(N); //Массивы координат точек

//Зададим наши точки
x[0] = 1.0; y[0] = 2.0;
x[1] = 4.0; y[1] = 1.0;
x[2] = 3.0; y[2] = 0.0;
x[3] = 0.5; y[3] = 2.2;
x[4] = 1.5; y[4] = 0.7;
ui->widget->clearGraphs();//Если нужно, но очищаем все графики

//Добавляем один график в widget
ui->widget->addGraph();

//Говорим, что отрисовать нужно график по нашим двум массивам x и y
ui->widget->graph(0)->setData(x, y);
ui->widget->graph(0)->setPen(QColor(50, 50, 50, 255));//задаем цвет точки
ui->widget->graph(0)->setLineStyle(QCPGraph::lsNone);//убираем линии

//формируем вид точек
ui->widget->graph(0)->setScatterStyle(QCPScatterStyle(QCPScatterStyle::ssCircle, 4));

//Подписываем оси Ox и Oy
ui->widget->xAxis->setLabel("x");
ui->widget->yAxis->setLabel("y");

//Установим область, которая будет показываться на графике
ui->widget->xAxis->setRange(-1, 5);//Для оси Ox
ui->widget->yAxis->setRange(-1, 3);//Для оси Oy

//И перерисуем график на нашем widget
ui->widget->replot();
```

![Точечный график из массивов](img/result_03.png)

## Старый пример

До обновления статьи 2015-12-01 тут был вот такой пример:

```cpp
 // generate some data:
QVector<double> x(101), y(101); // initialize with entries 0..100
for (int i = 0; i < 101; ++i) {
  x[i] = i/50.0 - 1; // x goes from -1 to 1
  y[i] = x[i] * x[i]; // let's plot a quadratic function
}

// create graph and assign data to it:
ui->widget->addGraph();
ui->widget->graph(0)->setData(x, y);

// give the axes some labels:
ui->widget->xAxis->setLabel("x");
ui->widget->yAxis->setLabel("y");

// set axes ranges, so we see all data:
ui->widget->xAxis->setRange(-1, 1);
ui->widget->yAxis->setRange(0, 1);
ui->widget->replot();
```
