---
title: 'SQL: SQL и типы данных C++ (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6a137c4f648f518420d06f5cbd98ea189a030aee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095412"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL. Типы данных SQL и C++ (ODBC)
> [!NOTE]
>  Эти сведения относятся к классам MFC ODBC. При работе с классами MFC DAO см. в разделе «Сравнение Microsoft Jet базы данных ядра SQL и ANSI SQL» справки DAO.  
  
 Следующая таблица сопоставление типов данных ANSI SQL в типы данных C++. Это расширяет сведения о языке C, приведенные в приложении D *ODBC SDK* *Справочник программиста* на компакт-диске библиотеки MSDN. Мастеры управление большинство сопоставление типов данных для вас. Если мастер не используется, можно использовать сведения о сопоставлении, помогающих писать код сопоставления полей вручную.  
  
### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>Типы данных ANSI SQL, которые сопоставлены с типами данных C++  
  
|Тип данных ANSI SQL|Тип данных в C++|  
|------------------------|---------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**ЦЕЛОЕ ЧИСЛО СО ЗНАКОМ**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**ЧИСЛОВОЙ**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**ДВОИЧНЫЙ**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**ВРЕМЯ**|**CTime CString**|  
|**ОТМЕТКА ВРЕМЕНИ**|**CTime CString**|  
  
 1. ANSI **ДЕСЯТИЧНОЕ** и **ЧИСЛОВОЕ** сопоставляются `CString` из-за **SQL_C_CHAR** тип передачи ODBC по умолчанию.  
  
 2. По умолчанию при сопоставлении усекаются символьные данные длиной более 255 знаков `CString`. Можно увеличить длину усечения, явно задав `nMaxLength` аргумент `RFX_Text`.  
  
 3. По умолчанию при сопоставлении усекаются двоичных данных длиной более 255 знаков `CByteArray`. Можно увеличить длину усечения, явно задав `nMaxLength` аргумент `RFX_Binary`.  
  
 Если вы не используете библиотеку курсоров ODBC, могут возникнуть проблемы при попытке обновить два или несколько полей переменной длины типа long, с помощью драйвера ODBC для Microsoft SQL Server и классы баз данных MFC ODBC. Типы ODBC **SQL_LONGVARCHAR** и **SQL_LONGVARBINARY**, сопоставление текста и изображений типов SQL Server. Объект `CDBException` возникает исключение при обновлении двух или нескольких полей переменной длины типа long в одном вызове на `CRecordset::Update`. Таким образом, не обновляются несколько столбцов типа long одновременно с `CRecordset::Update`. Одновременно обновить несколько столбцов типа long с помощью API ODBC **SQLPutData**. Можно также использовать библиотеку курсоров ODBC, но это не рекомендуется для драйверов, как драйвер SQL Server, которые поддерживают курсоры и не обязательно библиотеку курсоров.  
  
 При использовании библиотеки курсоров ODBC с помощью классов баз данных MFC ODBC и драйвер ODBC для Microsoft SQL Server, **ASSERT** могут возникнуть вместе с `CDBException` Если вызов `CRecordset::Update` следует вызовом `CRecordset::Requery`. Вместо этого необходимо вызвать `CRecordset::Close` и `CRecordset::Open` вместо `CRecordset::Requery`. Другое решение — не использовать библиотеку курсоров ODBC, так как SQL Server и драйвер ODBC для SQL Server предоставляют встроенную поддержку для курсоров изначально и не требуется библиотека курсоров ODBC.  
  
## <a name="see-also"></a>См. также  
 [SQL](../../data/odbc/sql.md)   
 [SQL. Выполнение прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)