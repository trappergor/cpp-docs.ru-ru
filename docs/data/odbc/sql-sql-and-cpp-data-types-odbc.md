---
title: SQL. Типы данных SQL и C++ (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: cffe44b832ac1eb28d368072b8f0e92ea9f57feb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374477"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL. Типы данных SQL и C++ (ODBC)

> [!NOTE]
> Эта информация относится к классам ODBC библиотеки MFC. Если вы работаете с классами MFC DAO, см.

В следующей таблице отогражны типы данных ANSI S'L к типам данных СЗЗ. Это дополняет информацию о языке C, приведенную в приложении D *от Справки программиста* *ODBC SDK* о CD библиотеки MSDN. Мастера управляют большинством картографических данных для вас. Если вы не используете мастера, вы можете использовать отображение информации, чтобы помочь вам написать код обмена поля вручную.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>Типы данных АНСИ СЗЛ, отображаемые по типам данных СЗ

|Тип данных ANSI S'L|Тип данных в C++|
|------------------------|---------------------|
|**Char**|`CString`|
|**Десятичных**|`CString`1|
|**SMALLINT**|**INT**|
|**Реальные**|**FLOAT**|
|**Целое число**|**Длинные**|
|**Плавать**|**double**|
|**Двухместный**|**double**|
|**Числовые**|`CString`1|
|**Varchar**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**Разрядной**|**Bool**|
|**Tinyint**|**Байт**|
|**Bigint**|`CString`1|
|**Двоичном**|`CByteArray`|
|**Varbinary**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**Дата**|`CTime`, `CString`|
|**Время**|`CTime`, `CString`|
|**Timestamp**|`CTime`, `CString`|

1. ANSI **DECIMAL** и **NUMERIC** карта, `CString` потому что **SQL_C_CHAR** является типом передачи ODBC по умолчанию.

2. Данные о персонажах за 255 символами усечены по умолчанию при отображении. `CString` Вы можете расширить длину усечения, `RFX_Text`явно установив аргумент *nMaxLength.*

3. Двоичные данные за 255 символов усечены по умолчанию при отображении. `CByteArray` Вы можете расширить длину усечения, `RFX_Binary`явно установив аргумент *nMaxLength.*

Если вы не используете библиотеку курсоров ODBC, вы можете столкнуться с проблемой при попытке обновить два или более длинных полей с переменной длиной с помощью драйвера Microsoft S'L Server ODBC и классов баз данных MFC ODBC. Типы ODBC, **SQL_LONGVARCHAR** и **SQL_LONGVARBINARY**, карта для текста и изображения типов сервера S'L. A `CDBException` брошен, если вы обновите два или более `CRecordset::Update`длинных полей с переменной длиной на одном и том же вызове. Таким образом, не обновляйте несколько длинных столбцов одновременно с `CRecordset::Update`. Вы можете обновить несколько длинных столбцов `SQLPutData`одновременно с API ODBC. Вы также можете использовать библиотеку курсоров ODBC, но это не рекомендуется для драйверов, таких как драйвер s'L Server, которые поддерживают курсоры и не нуждаются в библиотеке курсоров.

Если вы используете библиотеку курсоров ODBC с классами баз данных MFC ODBC и драйвером Microsoft `CRecordset::Update` S'L `CRecordset::Requery`Server ODBC, **assert** может произойти вместе с вызовом, `CDBException` чтобы следовать вызову. Вместо этого, `CRecordset::Open` вызов `CRecordset::Requery` `CRecordset::Close` и вместо . Другим решением является не использование библиотеки курсоров ODBC, так как s'L Server и драйвер S'L Server ODBC обеспечивают родную поддержку курсоров на родине, и библиотека курсора ODBC не нужна.

## <a name="see-also"></a>См. также раздел

[SQL](../../data/odbc/sql.md)<br/>
[SQL. Выполнение прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
