---
title: "Программное создание таблицы в источнике данных ODBC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 43be9c8a2339bb47d598304145a8c34f391b11c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Источник данных. Создание таблицы в источнике данных ODBC программным путем
В этом разделе объясняется, как создать таблицу для данных источника, используя `ExecuteSQL` функции-члена класса `CDatabase`, передавая функции строку, содержащую **CREATE TABLE** инструкции SQL.  
  
 Общие сведения об источниках данных ODBC в MFC см. в разделе [источника данных (ODBC)](../../data/odbc/data-source-odbc.md). Раздел [источника данных: Программная настройка источника данных ODBC](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) описано создание источников данных.  
  
 При наличии созданные источник данных, можно легко создавать таблицы, используя `ExecuteSQL` функции-члена и **CREATE TABLE** инструкции SQL. Например, если у вас `CDatabase` объекта с именем `myDB`, можно использовать следующий код MFC для создания таблицы:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 Данный пример кода создает таблицу с именем «ОФИСОВ» в подключении к источнику данных Microsoft Access, поддерживаемом `myDB`; таблица содержит два поля «OfficeID» и «OfficeName».  
  
> [!NOTE]
>  Типы полей, указанные в **CREATE TABLE** инструкции SQL может различаться в зависимости от драйвера ODBC, который вы используете. Программа Microsoft Query (поставляется с Visual C++ 1.5) — один из способов выяснить, какие поля доступны для источника данных. В Microsoft Query, нажмите кнопку **файл**, нажмите кнопку **Table_Definition**, выберите таблицу из источника данных и посмотрите на тип, показанный в **тип** поле со списком. Синтаксис SQL также используется для создания индексов.  
  
## <a name="see-also"></a>См. также  
 [Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)