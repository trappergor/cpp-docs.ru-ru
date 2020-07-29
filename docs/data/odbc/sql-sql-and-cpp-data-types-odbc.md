---
title: SQL. Типы данных SQL и C++ (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 424ae09f6462d4d34b5a847fc210f9329e76d788
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218342"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL. Типы данных SQL и C++ (ODBC)

> [!NOTE]
> Эта информация относится к классам ODBC библиотеки MFC. Если вы работаете с классами MFC DAO, ознакомьтесь с разделом «Сравнение Microsoft Jet ядро СУБД SQL и ANSI SQL» справки DAO.

Следующая таблица сопоставляет типы данных ANSI SQL с типами данных C++. Это дополняет сведения о языке C, представленные в приложении D [справочной документации программиста ODBC](/sql/odbc/reference/odbc-programmer-s-reference) . Мастера управляют большинством сопоставлений типов данных. Если мастер не используется, можно использовать сведения о сопоставлении, чтобы облегчить написание кода обмена поля вручную.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>Типы данных SQL ANSI, сопоставленные с типами данных C++

|Тип данных SQL ANSI|Тип данных в C++|
|------------------------|---------------------|
|**ТИПА**|`CString`|
|**DECIMAL**|`CString`одного|
|**SMALLINT**|**`int`**|
|**REAL**|**`float`**|
|**ЦЕЛО**|**`long`**|
|**СДЕЛАТЬ**|**`double`**|
|**Дважды**|**`double`**|
|**ISNUMERIC**|`CString`одного|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**ВЕРСИЙ**|**ЛОГИЧЕСКОМ**|
|**TINYINT**|**ДВУХБАЙТОВЫХ**|
|**BIGINT**|`CString`одного|
|**ДВОИЧНЫЙ**|`CByteArray`|
|**VARBINARY**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**ТАЙМАУТ**|`CTime`, `CString`|
|**timestamp**|`CTime`, `CString`|

1. **Десятичное** и **числовое** сопоставляется в кодировке ANSI, `CString` так как **SQL_C_CHAR** является типом обмена ODBC по умолчанию.

2. Символьные данные, превышающие 255 символов, усекаются по умолчанию при сопоставлении с `CString` . Длину усечения можно расширить, явно задав аргумент *нмаксленгс* в параметре `RFX_Text` .

3. Двоичные данные, превышающие 255 символов, усекаются по умолчанию при сопоставлении с `CByteArray` . Длину усечения можно расширить, явно задав аргумент *нмаксленгс* в параметре `RFX_Binary` .

Если библиотека курсоров ODBC не используется, может возникнуть проблема при попытке обновить два или более длинные поля переменной длины с помощью драйвера Microsoft SQL Server ODBC и классов базы данных ODBC MFC. Типы ODBC, **SQL_LONGVARCHAR** и **SQL_LONGVARBINARY**сопоставляются с типами SQL Server текста и изображений. `CDBException`Исключение возникает при обновлении двух или более длинных полей переменной длины в одном вызове `CRecordset::Update` . Поэтому не обновляйте несколько столбцов Long одновременно с `CRecordset::Update` . С помощью API ODBC можно одновременно обновить несколько столбцов типа long `SQLPutData` . Можно также использовать библиотеку курсоров ODBC, но это не рекомендуется делать для драйверов, таких как драйвер SQL Server, которые поддерживают курсоры и не нуждаются в библиотеке курсоров.

Если вы используете библиотеку курсоров ODBC с классами базы данных ODBC MFC и драйвером Microsoft SQL Server ODBC, **утверждение** может возникнуть вместе с, `CDBException` Если вызов выполняется `CRecordset::Update` после вызова метода `CRecordset::Requery` . Вместо этого вызывайте метод `CRecordset::Close` и, `CRecordset::Open` а не `CRecordset::Requery` . Другое решение — не использовать библиотеку курсоров ODBC, так как SQL Server и драйвер ODBC SQL Server обеспечивают встроенную поддержку курсоров в собственном режиме, а библиотека курсоров ODBC не требуется.

## <a name="see-also"></a>См. также раздел

[SQL](../../data/odbc/sql.md)<br/>
[SQL: выполнение прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
