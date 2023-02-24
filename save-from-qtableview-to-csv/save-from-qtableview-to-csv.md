---
date: 2014-05-06
categories: [it, programming]
tags: [Qt, CSV, Таблица, C++, Работа с файлами]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2014/blob/main/save-from-qtableview-to-csv/save-from-qtableview-to-csv.md
url: https://harrix.dev/ru/blog/2014/save-from-qtableview-to-csv/
---

# Как сохранять из QTableView данные в CSV формат

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

Получили вот это:

![Открытый CSV файл](img/excel.png)

В статье [Как вывести данные в QTableView в Qt](https://github.com/Harrix/harrix.dev-blog-2014/blob/main/output-data-to-qtableview/output-data-to-qtableview.md) узнаете, как добавлять данные в QTableView.
