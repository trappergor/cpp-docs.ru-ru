---
title: SQL. Типы данных SQL и C++ (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 1c1ce908b5c8d345906d49adc79e322225ed49f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212619"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL. Типы данных SQL и C++ (ODBC)

> [!NOTE]
>  Эта информация относится к классам ODBC библиотеки MFC. Если вы работаете с классами MFC DAO, ознакомьтесь с разделом «Сравнение Microsoft Jet ядро СУБД SQL и ANSI SQL» справки DAO.

Следующая таблица сопоставляет типы данных ANSI SQL с C++ типами данных. Это дополняет сведения о языке C, представленные в приложении г из *ODBC SDK* *справочника по программированию* SDK для ODBC на компакт-диске библиотеки MSDN. Мастера управляют большинством сопоставлений типов данных. Если мастер не используется, можно использовать сведения о сопоставлении, чтобы облегчить написание кода обмена поля вручную.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>Типы данных SQL ANSI, сопоставленные с C++ типами данных

|Тип данных SQL ANSI|Тип данных в C++|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**DECIMAL**|`CString` 1|
|**SMALLINT**|**int**|
|**REAL**|**float**|
|**INTEGER**|**long**|
|**FLOAT**|**double**|
|**DOUBLE**|**double**|
|**NUMERIC**|`CString` 1|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**BIT**|**BOOL**|
|**TINYINT**|**BYTE**|
|**BIGINT**|`CString` 1|
|**ДВОИЧНЫЙ**|`CByteArray`|
|**VARBINARY**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**TIME**|`CTime`, `CString`|
|**TIMESTAMP**|`CTime`, `CString`|

1. **Десятичное** и **числовое** сопоставление ANSI с `CString`, поскольку **SQL_C_CHAR** является типом обмена по умолчанию ODBC.

2. Символьные данные, превышающие 255 символов, усекаются по умолчанию при сопоставлении с `CString`. Длину усечения можно расширить, явно задав аргумент *нмаксленгс* для `RFX_Text`.

3. Двоичные данные, превышающие 255 символов, усекаются по умолчанию при сопоставлении с `CByteArray`. Длину усечения можно расширить, явно задав аргумент *нмаксленгс* для `RFX_Binary`.

Если библиотека курсоров ODBC не используется, может возникнуть проблема при попытке обновить два или более длинные поля переменной длины с помощью драйвера Microsoft SQL Server ODBC и классов базы данных ODBC MFC. Типы ODBC, **SQL_LONGVARCHAR** и **SQL_LONGVARBINARY**сопоставляются с типами SQL Server текста и изображений. При обновлении двух или более длинных полей переменной длины в одном вызове `CRecordset::Update`возникает исключение `CDBException`. Поэтому не обновляйте несколько столбцов Long одновременно с `CRecordset::Update`. С помощью `SQLPutData`API ODBC можно одновременно обновить несколько столбцов Long. Можно также использовать библиотеку курсоров ODBC, но это не рекомендуется делать для драйверов, таких как драйвер SQL Server, которые поддерживают курсоры и не нуждаются в библиотеке курсоров.

Если вы используете библиотеку курсоров ODBC с классами базы данных ODBC MFC и драйвером Microsoft SQL Server ODBC, то **утверждение** может происходить вместе с `CDBException`, если вызов `CRecordset::Update` выполняется после вызова `CRecordset::Requery`. Вместо этого вызывайте `CRecordset::Close` и `CRecordset::Open`, а не `CRecordset::Requery`. Другое решение — не использовать библиотеку курсоров ODBC, так как SQL Server и драйвер ODBC SQL Server обеспечивают встроенную поддержку курсоров в собственном режиме, а библиотека курсоров ODBC не требуется.

## <a name="see-also"></a>См. также раздел

[SQL](../../data/odbc/sql.md)<br/>
[SQL. Выполнение прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
