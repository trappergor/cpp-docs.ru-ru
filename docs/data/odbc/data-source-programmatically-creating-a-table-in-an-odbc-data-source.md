---
title: Программное создание таблицы в источнике данных ODBC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b4db77aae6050f5612c7da14c061e49db142669e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106016"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Источник данных. Создание таблицы в источнике данных ODBC программным путем

В этом разделе объясняется, как создать таблицу для данных источник данных, с помощью `ExecuteSQL` функция-член класса `CDatabase`, передав строку, содержащую функцию **CREATE TABLE** инструкции SQL.  
  
Общие сведения об источниках данных ODBC в MFC см. в разделе [источника данных (ODBC)](../../data/odbc/data-source-odbc.md). Раздел [источника данных: Программная настройка источника данных ODBC](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) описано создание источников данных.  
  
Если у вас есть созданные источник данных, можно легко создавать таблицы с помощью `ExecuteSQL` функция-член и **CREATE TABLE** инструкции SQL. Например, если у вас есть `CDatabase` объект с именем `myDB`, можно использовать следующий код MFC для создания таблицы:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
Данный пример кода создает таблицу с именем «ОФИСЫ» в подключении к источнику данных Microsoft Access, обслуживается `myDB`; таблица содержит два поля «OfficeID» и «OfficeName.»  
  
> [!NOTE]
>  Типы полей, указанные в **CREATE TABLE** инструкции SQL может различаться в зависимости от драйвера ODBC, который вы используете. Программа Microsoft Query (в состав Visual C++ 1.5) — один из способов определить, какие типы полей, доступных для источника данных. Microsoft запрос, нажмите кнопку **файл**, нажмите кнопку **Table_Definition**, выберите таблицу из источника данных и просмотрите типа, отображаемое в **тип** поле со списком. Синтаксис SQL также используется для создания индексов.  
  
## <a name="see-also"></a>См. также  

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)