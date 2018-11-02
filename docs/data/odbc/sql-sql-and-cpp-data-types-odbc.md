---
title: SQL. Типы данных SQL и C++ (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 6767d009ca376d8e8579baf32f2c9af1e282abce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649505"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL. Типы данных SQL и C++ (ODBC)

> [!NOTE]
>  Эти сведения относятся к классам ODBC библиотеки MFC. Если вы работаете с классами MFC DAO, см. в разделе «Сравнения Microsoft Jet базы данных ядра SQL и ANSI SQL» в справке DAO.

Следующая таблица сопоставляет типы данных ANSI SQL в типы данных C++. Это расширяет сведения о языке C, в приложении D *ODBC SDK* *справочнике программиста* на компакт-диске библиотеки MSDN. Мастера управления большинство сопоставление типов данных для вас. Если вы не используете мастер, можно использовать сведения о сопоставлении и помогает писать код сопоставления полей вручную.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>Типы данных ANSI SQL, которые сопоставлены с типами данных C++

|Тип данных ANSI SQL|Тип данных в C++|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**DECIMAL**|`CString` 1|
|**SMALLINT**|**int**|
|**REAL**|**float**|
|**ЦЕЛОЕ ЧИСЛО**|**long**|
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
|**ВРЕМЯ**|`CTime`, `CString`|
|**МЕТКА ВРЕМЕНИ**|`CTime`, `CString`|

1. ANSI **ДЕСЯТИЧНОЕ** и **ЧИСЛОВЫХ** сопоставляются `CString` поскольку **SQL_C_CHAR** тип передачи ODBC по умолчанию.

2. Символьные данные длиной более 255 знаков будут усечены по умолчанию при сопоставлении `CString`. Вы можете расширить длину усечения, явно задав *nMaxLength* аргумент `RFX_Text`.

3. По умолчанию при сопоставлении усекаются двоичные данные длиной более 255 знаков `CByteArray`. Вы можете расширить длину усечения, явно задав *nMaxLength* аргумент `RFX_Binary`.

Если вы не используете библиотеки курсоров ODBC, может возникнуть ошибка при попытке обновить два или несколько полей переменной длины типа long, с помощью драйвера Microsoft SQL Server ODBC и классы баз данных MFC ODBC. Типы ODBC, **SQL_LONGVARCHAR** и **SQL_LONGVARBINARY**, сопоставляются с текста и изображений типов SQL Server. Объект `CDBException` возникает исключение при обновлении двух или более полей долго переменной длины на тот же вызов `CRecordset::Update`. Таким образом, не обновляются несколько столбцов типа long одновременно с `CRecordset::Update`. Одновременно обновить несколько столбцов типа long с API-Интерфейс ODBC `SQLPutData`. Также можно использовать библиотеку курсоров ODBC, но это не рекомендуется для драйверов, как драйвер SQL Server, которые поддерживают курсоры и не обязательно библиотеку курсоров.

При использовании библиотеки курсоров ODBC с классы баз данных MFC ODBC и драйвер ODBC для Microsoft SQL Server, **ASSERT** могут возникнуть вместе с `CDBException` Если вызов `CRecordset::Update` после вызова функции для `CRecordset::Requery`. Вместо этого необходимо вызвать `CRecordset::Close` и `CRecordset::Open` вместо `CRecordset::Requery`. Другим решением является не следует использовать библиотеку курсоров ODBC, так как SQL Server и драйвер ODBC для SQL Server предоставляют встроенную поддержку для курсоров в собственном коде, и библиотека курсоров ODBC не требуется.

## <a name="see-also"></a>См. также

[SQL](../../data/odbc/sql.md)<br/>
[SQL. Выполнение прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)