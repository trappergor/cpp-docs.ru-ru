---
title: 'Обмен полями записей: Использование функций RFX'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
ms.openlocfilehash: dc717336a5279e7eda1b7c39b19a7c76f9055cd3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035988"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Обмен полями записей: Использование функций RFX

В этом разделе описываются способы использования функции RFX, составляющих тело вашей `DoFieldExchange` переопределить.

> [!NOTE]
>  Этот раздел относится к классам, производным от [CRecordset](../../mfc/reference/crecordset-class.md) в какой строке массовой выборка не был реализован. Если вы используете выборка строк, реализуется блочный обмен полей записей (Bulk RFX). Bulk RFX аналогичен RFX. Сведения о различиях, см. в разделе [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Глобальные функции RFX обмена данными между столбцами на члены данных источника и поля данных в набор записей. Записи в наборе записей вызовы функции RFX [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) функция-член. В этом разделе кратко описаны функции и показаны типы данных, для RFX доступных функций. [Технические заметки 43](../../mfc/tn043-rfx-routines.md) описывается, как создавать собственные функции RFX для дополнительных типов данных.

##  <a name="_core_rfx_function_syntax"></a> Синтаксис функции RFX

Каждая функция RFX принимает три параметра (и некоторые принимает необязательный параметр четвертый и пятый):

- Указатель на [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) объекта. Следует просто передать `pFX` указатель передан в `DoFieldExchange`.

- Имя столбца, как он отображается в источнике данных.

- Имя соответствующего элемента данных поля или элемента данных параметра в классе набора записей.

- (Необязательно) В некоторых функций, максимальная длина строки или массива, передаваемый. По умолчанию используется 255 байт, но может потребоваться изменить его. Максимальный размер основан на максимальный размер `CString` объекта — **INT_MAX** (2 147 483 647) байт, но, скорее всего, приведет к ограничивается драйвера.

- (Необязательно) В `RFX_Text` функции, иногда пятый параметр используется для указания типа данных столбца.

Дополнительные сведения см. в разделе функций RFX [макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md) в *Справочник по библиотеке классов*. Пример, из которых может потребоваться специальное использование параметров, см. в разделе [набор записей: Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md).

##  <a name="_core_rfx_data_types"></a> Типы данных RFX

Библиотека классов предоставляет функции RFX для обмена данными различных типов между источником данных и набором записей. В следующем списке перечислены функции RFX по типу данных. В случаях, где необходимо написать свои собственные функции RFX выберите один из этих функций по типам данных.

|Функция|Тип данных|
|--------------|---------------|
|`RFX_Bool`|**BOOL**|
|`RFX_Byte`|**BYTE**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**long**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|


Дополнительные сведения см. в документации функции RFX под [макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md) в *Справочник по библиотеке классов*. Сведения о сопоставлении типов данных C++ в типы данных SQL, см. в таблице, ANSI SQL данные типы сопоставляются с типами данных C++ в [SQL: SQL и типы данных C++ (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md).

## <a name="see-also"></a>См. также

[Обмен данными полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Набор записей. Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Набор записей. Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)