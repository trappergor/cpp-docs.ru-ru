---
title: Программное создание таблицы в источнике данных ODBC
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 25c975560d6a73ce67294d97830b2f5bec9cd635
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213282"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Источник данных. Создание таблицы в источнике данных ODBC программным путем

В этом разделе объясняется, как создать таблицу для источника данных с помощью функции-члена `ExecuteSQL` класса `CDatabase`, передав функции строку, содержащую **CREATE TABLE** инструкцию SQL.

Общие сведения об источниках данных ODBC в MFC см. в разделе [Data Source (ODBC)](../../data/odbc/data-source-odbc.md). Раздел [источник данных. Программная настройка источника данных ODBC](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) описывает создание источников данных.

Если источник данных установлен, можно легко создавать таблицы с помощью функции члена `ExecuteSQL` и инструкции **CREATE TABLE** SQL. Например, если имеется объект `CDatabase` с именем `myDB`, для создания таблицы можно использовать следующий код MFC:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Этот пример кода создает таблицу с именем "офисы" в подключении к источнику данных Microsoft Access, поддерживаемом `myDB`; Таблица содержит два поля "Оффицеид" и "Оффиценаме".

> [!NOTE]
>  Типы полей, указанные в инструкции SQL **CREATE TABLE** , могут различаться в зависимости от используемого драйвера ODBC. Программа Microsoft Query (распространяемая с Visual C++ 1,5) — это один из способов узнать, какие типы полей доступны для источника данных. В Microsoft Query выберите **файл**, щелкните **Table_Definition**, выберите таблицу из источника данных и посмотрите на тип, показанный в поле со списком **тип** . Для создания индексов также существует синтаксис SQL.

## <a name="see-also"></a>См. также раздел

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)
