---
title: Обмен полями записей. Использование функций RFX
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
ms.openlocfilehash: f1afded360cfeff564f1f3d8bb9b294aa33cb733
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367129"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>Обмен полями записей. Использование функций RFX

Эта тема объясняет, как использовать вызовы функции RFX, которые составляют тело вашего `DoFieldExchange` переопределения.

> [!NOTE]
> Эта тема относится к классам, полученным из [CRecordset,](../../mfc/reference/crecordset-class.md) в которых объем строки извлечения не был реализован. Если вы используете пакетное получение строк, реализуется пакетный обмен полями записей (Bulk RFX). Bulk RFX аналогичен RFX. Чтобы понять различия, [см.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

Глобальные функции RFX обмениваются данными между столбиками источника данных и полевыми участниками данных в вашем наборе записей. Вы пишете вызовы функции RFX в функции участника [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) вашего записного набора. В этой теме кратко описаны функции и показаны типы данных, для которых доступны функции RFX. [В техническом примечании 43](../../mfc/tn043-rfx-routines.md) описывается, как писать собственные функции RFX для дополнительных типов данных.

## <a name="rfx-function-syntax"></a><a name="_core_rfx_function_syntax"></a>Syntax функции RFX

Каждая функция RFX имеет три параметра (а некоторые принимают дополнительный четвертый или пятый параметр):

- Указатель на объект [CFieldExchange.](../../mfc/reference/cfieldexchange-class.md) Вы просто проходите по `pFX` `DoFieldExchange`указателю, передаваемому к .

- Название столбца, как она отображается на источнике данных.

- Имя соответствующего члена данных поля или члена данных параметра в классе recordset.

- (Необязательно) В некоторых функциях передается максимальная длина строки или массива. Это по умолчанию до 255 байтов, но вы можете изменить его. Максимальный размер основан на максимальном `CString` размере объекта - **INT_MAX** (2 147 483 647) байтов, - но вы, вероятно, столкнетесь с ограничениями драйвера до этого размера.

- (Необязательно) В `RFX_Text` функции иногда используется пятый параметр для определения типа столбца данных.

Для получения дополнительной информации смотрите функции RFX в [рамках Макрос и Глобалс](../../mfc/reference/mfc-macros-and-globals.md) в *справочнике библиотеки класса*. Например, когда можно использовать параметры с особым использованием, [см.](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

## <a name="rfx-data-types"></a><a name="_core_rfx_data_types"></a>Типы данных RFX

Библиотека классов предоставляет функции RFX для передачи различных типов данных между источником данных и наборами записей. Следующий список обобщает функции RFX по типу данных. В тех случаях, когда необходимо написать свои собственные вызовы функции RFX, выберите из этих функций по типу данных.

|Компонент|Тип данных|
|--------------|---------------|
|`RFX_Bool`|**Bool**|
|`RFX_Byte`|**Байт**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**FLOAT**|
|`RFX_Int`|**INT**|
|`RFX_Long`|**Длинные**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|

Для получения дополнительной информации смотрите документацию функции RFX в [рамках Макрос а также globals](../../mfc/reference/mfc-macros-and-globals.md) в *справочнике библиотеки класса*. Для получения информации о том, как типы данных СЗЗ к типам данных СЗЛ, см. таблицу ТИПОВ данных АНСИ СЗЛ, отображаемую на типах данных СЗЛ в [СЗЛ: типах данных СЗЛ и СЗЗ (ODBC).](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

## <a name="see-also"></a>См. также раздел

[Рекордная полевая биржа (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Обмен данными с полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Набор записей. Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Набор записей. Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)
