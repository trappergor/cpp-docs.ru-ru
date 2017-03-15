---
title: "Источник данных. Создание таблицы в источнике данных ODBC программным путем | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "источники данных (ODBC), создание таблиц"
  - "программное создание таблиц ODBC [C++]"
  - "таблицы [C++]"
  - "таблицы [C++], создание программным способом"
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Источник данных. Создание таблицы в источнике данных ODBC программным путем
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе объясняется, как создать таблицу для источника данных, используя функцию\-член `ExecuteSQL` класса `CDatabase`, передавая функции строку, содержащую инструкцию SQL **CREATE TABLE**.  
  
 Общие сведения об источниках данных ODBC в MFC см. в разделе [Источник данных \(ODBC\)](../../data/odbc/data-source-odbc.md).  В разделе [Источник данных. Настройка источника данных ODBC программным путем](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) описано создание источников данных.  
  
 Если имеются созданные источник данных, можно легко создавать таблицы, используя функцию\-член `ExecuteSQL` и инструкцию SQL **CREATE TABLE**.  Например, если имеется объект `CDatabase` с именем `myDB`, можно воспользоваться следующим кодом MFC для создания таблицы:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 В этом примере кода создается таблица с именем "OFFICES" в подключении к источнику данных Microsoft Access, поддерживаемом объектом `myDB`; таблица содержит два поля: "OfficeID" и "OfficeName".  
  
> [!NOTE]
>  Типы полей, указанные в инструкции SQL **CREATE TABLE**, могут отличаться в зависимости от используемого драйвера ODBC.  Программа Microsoft Query \(распространяемая с Visual C\+\+ 1.5\) — это один из способов обнаружения доступных полей в источнике данных.  В Microsoft Query последовательно щелкните **Файл**, **Table\_Definition**, выберите в источнике данных таблицу и посмотрите, какой тип отображен в поле со списком **Тип**.  Синтаксис SQL также используется для создания указателей.  
  
## См. также  
 [Источник данных \(ODBC\)](../../data/odbc/data-source-odbc.md)