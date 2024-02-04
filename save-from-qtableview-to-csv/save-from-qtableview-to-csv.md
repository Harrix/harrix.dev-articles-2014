---
date: 2014-05-06
categories: [it, programming]
tags: [Qt, CSV, Таблица, C++, Работа с файлами]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2014/blob/main/save-from-qtableview-to-csv/save-from-qtableview-to-csv.md
permalink: https://harrix.dev/ru/articles/2014/save-from-qtableview-to-csv/
lang: ru
attribution:
  - {
      author: Christlich Soziale Volkspartei,
      author-site: "https://de.wikipedia.org/wiki/Christlich_Soziale_Volkspartei",
      license: Public domain,
      license-url: "https://en.wikipedia.org/wiki/Public_domain",
      permalink: "https://ru.wikipedia.org/wiki/%D0%A4%D0%B0%D0%B9%D0%BB:CSV_Logo.svg",
      permalink-date: 2019-03-24,
      name: CSV Logo.svg,
    }
---

# Как сохранять из QTableView данные в CSV формат

![Featured image](featured-image.svg)

В статье описана функция, которая вам поможет сохранять из таблицы данные в CSV формат, который читается Excel.

Написал вот такую функцию. Она сохраняет всё содержимое таблицы, включая вертикальный столбец и горизонтальную строку заголовков. Единственно, чего нет, так как это экранирования двойных кавычек:

```cpp
void MainWindow::saveAsCSV(QString filename)
{
  QFile f(filename);

  if( f.open( QIODevice::WriteOnly ) )
  {
    QTextStream ts( &f );
    QStringList strList;

    strList << "\" \"";
    for( int c = 0; c < ui->tableView->horizontalHeader()->count(); ++c )
      strList << "\""+ui->tableView->model()->headerData(c, Qt::Horizontal).toString()+"\"";
    ts << strList.join( ";" )+"\n";

    for( int r = 0; r < ui->tableView->verticalHeader()->count(); ++r )
    {
      strList.clear();
      strList << "\""+ui->tableView->model()->headerData(r, Qt::Vertical).toString()+"\"";
      for( int c = 0; c < ui->tableView->horizontalHeader()->count(); ++c )
      {
        strList << "\""+ui->tableView->model()->data(ui->tableView->model()->index(r, c), Qt::DisplayRole).toString()+"\"";
      }
      ts << strList.join( ";" )+"\n";
    }
    f.close();
  }
}
```

Заголовочные файлы подключите те, что попросит Qt при компиляции.

Вот была такая таблица:

![Таблица с данными в Qt](img/qtableview.png)

_Рисунок 1 — Таблица с данными в Qt_

Получили вот это:

![Открытый CSV файл](img/excel.png)

_Рисунок 2 — Открытый CSV файл_

В статье [Как вывести данные в QTableView в Qt](https://github.com/Harrix/harrix.dev-articles-2014/blob/main/output-data-to-qtableview/output-data-to-qtableview.md) | [🡥](https://harrix.dev/ru/articles/2014/output-data-to-qtableview/) узнаете, как добавлять данные в QTableView.
