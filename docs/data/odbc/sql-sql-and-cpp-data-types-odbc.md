---
title: "SQL. Типы данных SQL и C++ (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "типы данных [C++], сравнение SQL и C++"
  - "SQL [C++], сравнение с типами данных [C++]"
  - "типы данных SQL [C++]"
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL. Типы данных SQL и C++ (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  В этом разделе приведены сведения, относящиеся к классам ODBC библиотеки MFC.  Сведения, относящиеся к классам DAO библиотеки MFC, см. в разделе "Сравнение ядра СУБД Microsoft Jet SQL и ANSI SQL" в справке DAO.  
  
 В следующей таблице приведено сопоставление типов данных ANSI SQL и C\+\+.  Эти сведения дополняют описание языка C, приведенное в приложении D *справочника программиста* *ODBC SDK* на компакт\-диске библиотеки MSDN.  Сопоставление большинства типов данных осуществляется автоматически с помощью мастеров.  Если мастер не используется, можно написать код сопоставления полей вручную на основе приведенных сведений о сопоставлении.  
  
### Сопоставление типов данных ANSI SQL и C\+\+  
  
|Тип данных ANSI SQL|Тип данных в C\+\+|  
|-------------------------|------------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**INTEGER**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**BINARY**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**TIME**|**CTime, CString**|  
|**TIMESTAMP**|**CTime, CString**|  
  
 1.  Типы ANSI **DECIMAL** и **NUMERIC** сопоставляются типу `CString`, поскольку в ODBC тип **SQL\_C\_CHAR** является используемым по умолчанию типом преобразования.  
  
 2.  Символьные типы данных длиной более 255 знаков по умолчанию усекаются при сопоставлении типу `CString`.  Чтобы увеличить длину усечения, явно установите аргумент `nMaxLength` метода `RFX_Text`.  
  
 3.  Двоичные типы данных длиной более 255 знаков по умолчанию усекаются при сопоставлении типу `CByteArray`.  Чтобы увеличить длину усечения, явно установите аргумент `nMaxLength` метода `RFX_Binary`.  
  
 Если не используется библиотека курсоров ODBC, может возникнуть ошибка при попытке обновления нескольких полей переменной длины типа Long с помощью драйвера Microsoft SQL Server ODBC и классов баз данных ODBC в библиотеке MFC.  Типы ODBC **SQL\_LONGVARCHAR** и **SQL\_LONGVARBINARY** сопоставляются типам текста и изображений SQL Server.  При попытке обновления нескольких полей переменной длины типа Long посредством одного вызова метода `CRecordset::Update` вызывается исключение `CDBException`.  В связи с этим не следует одновременно выполнять обновление нескольких столбцов типа Long посредством одного вызова метода `CRecordset::Update`.  Чтобы одновременно обновить несколько столбцов типа Long, используйте функцию **SQLPutData** интерфейса API ODBC.  Также можно использовать библиотеку курсоров ODBC \(не рекомендуется для таких драйверов, как драйвер SQL Server, которые поддерживают курсоры и не используют библиотеки курсоров\).  
  
 Если используется библиотека курсоров ODBC с классами баз данных ODBC библиотеки MFC и драйвером Microsoft SQL Server ODBC, при вызове метода `CRecordset::Update` после метода `CRecordset::Requery` могут одновременно возникнуть исключения **ASSERT** и `CDBException`.  В связи с этим следует вызывать методы `CRecordset::Close` и `CRecordset::Open` вместо метода `CRecordset::Requery`.  Также можно не использовать библиотеку курсоров ODBC, поскольку в драйвере SQL Server и SQL Server ODBC реализована собственная поддержка курсоров и не используется библиотека курсоров ODBC.  
  
## См. также  
 [SQL](../../data/odbc/sql.md)   
 [SQL. Выполнение прямых вызовов SQL \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)