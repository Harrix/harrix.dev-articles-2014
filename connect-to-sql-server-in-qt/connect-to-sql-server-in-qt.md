---
date: 2014-04-22
categories: [it, programming]
tags: [Qt, SQL Server, SQL, Базы данных, C++]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
---

# Как подключиться к базе данных в Microsoft SQL Server 2012 в Qt

Создана простейшая база данных в Microsoft SQL Server 2012. Надо было подключиться через Qt. Почему-то обычные приемы не работали. В статье показан тот код, который у меня заработал.

Сработал данный код. Подключаем вот это:

```cpp
#include "QtSql/QSqlDatabase"
#include "QDebug"
#include "QSqlError"
```

А потом в том месте, где хотим подключить базу данных (например, в кнопке) пишем код:

```cpp
QSqlDatabase db = QSqlDatabase::addDatabase("QODBC3");
db.setDatabaseName("DRIVER={SQL Server};SERVER=ENTER-HP;DATABASE=OOO_RKK;Trusted_Connection=yes;");
db.setUserName("sa");
db.setPassword("Password123");

if(!db.open()) {
  qDebug()<<"ERROR: "<<QSqlError(db.lastError()).text();
  ui->textEdit->insertPlainText(QSqlError(db.lastError()).text());
}
else {
  qDebug()<<"Ok";
  ui->textEdit->insertPlainText("Ok");
}
```

Разумеется, имя сервера, базы данных, пользователя и пароля у вас свои. Но в приведенном примере использованы стандартные имя пользователя и пароль, так что у вас подключится, если не меняли этого пользователя.
