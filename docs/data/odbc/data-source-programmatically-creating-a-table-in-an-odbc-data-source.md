---
title: Программно создать таблицу в источнике данных ODBC
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 6cf26cad7fe39f374daf371902525087b446658c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358842"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Источник данных. Создание таблицы в источнике данных ODBC программным путем

В этой теме объясняется, как создать `ExecuteSQL` таблицу для `CDatabase`исходного кода данных, используя функцию члена класса, передав функцию строки, содержащей заявление **CREATE TABLE** S'L.

Для получения общей информации об источниках данных ODBC в МФК [см.](../../data/odbc/data-source-odbc.md) Тема [Источник данных: Программно налаживая источник данных ODBC](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) описывает создание источников данных.

При установлении источника данных можно легко `ExecuteSQL` создавать таблицы с помощью функции члена и оператора **CREATE TABLE** S'L. Например, если у `CDatabase` вас `myDB`был объект под названием, можно использовать следующий код MFC для создания таблицы:

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

Этот пример кода создает таблицу под названием "OFFICES" `myDB`в доступе к данным Microsoft Access, поддерживаемом; таблица содержит два поля "OfficeID" и "OfficeName".

> [!NOTE]
> Типы полей, указанные в выписке **CREATE TABLE** S'L, могут варьироваться в зависимости от драйвера ODBC, который вы используете. Программа «Запрос аймек» (распределенная с помощью Visual C'1.5) — это один из способов узнать, какие типы полей доступны для источника данных. В запросе Майкрософт нажмите **«Файл»,** нажмите **Table_Definition,** выберите таблицу из источника данных и посмотрите на тип, показанный в комбо-коробке **Типа.** Для создания индексов также существует синтаксис S'L.

## <a name="see-also"></a>См. также раздел

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)
