---
title: Функции обмена данными полями записей
ms.date: 09/17/2019
f1_keywords:
- AFXDB/RFX_Binary
- AFXDB/RFX_Bool
- AFXDB/RFX_Byte
- AFXDB/RFX_Date
- AFXDB/RFX_Double
- AFXDB/RFX_Int
- AFXDB/RFX_Long
- AFXDB/RFX_LongBinary
- AFXDB/RFX_Single
- AFXDB/RFX_Text
- AFXDB/RFX_Binary_Bulk
- AFXDB/RFX_Bool_Bulk
- AFXDB/RFX_Byte_Bulk
- AFXDB/RFX_Date_Bulk
- AFXDB/RFX_Double_Bulk
- AFXDB/RFX_Int_Bulk
- AFXDB/RFX_Long_Bulk
- AFXDB/RFX_Single_Bulk
- AFXDB/RFX_Text_Bulk
- AFXDB/DFX_Binary
- AFXDB/DFX_Bool
- AFXDB/DFX_Byte
- AFXDB/DFX_Currency
- AFXDB/DFX_DateTime
- AFXDB/DFX_Double
- AFXDB/DFX_Long
- AFXDB/DFX_LongBinary
- AFXDB/DFX_Short
- AFXDB/DFX_Single
- AFXDB/DFX_Text
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- ODBC, bulk RFX data exchange functions [MFC]
- RFX (record field exchange), ODBC classes
- DFX (DAO record field exchange), data exchange functions [MFC]
- DFX functions [MFC]
- bulk RFX functions [MFC]
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- ODBC, RFX
- RFX (record field exchange), data exchange functions [MFC]
- RFX (record field exchange)
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
ms.openlocfilehash: bfd3ba64a33547b8a27e0f3bc896f39c94486464
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372975"
---
# <a name="record-field-exchange-functions"></a>Функции обмена данными полями записей

В этом разделе перечислены функции обмена полями записей (RFX, Bulk RFX и DFX), используемые для автоматизации передачи данных между объектом набора записей и источником данных и выполнения других операций с данными.

При использовании классов на основе ODBC и реализации массовой выборки строк необходимо вручную переопределить функцию-член `DoBulkFieldExchange``CRecordset` путем вызова функций Bulk RFX для каждого элемента данных, соответствующего столбцу источника данных.

Если вы не реализовали объемные строки, извлекающиеся в классах на основе ODBC, или если вы `DoFieldExchange` используете `CRecordset` классы на основе DAO (устаревшие), то ClassWizard переопределяет функцию участника или `CDaoRecordset` вызывая функции RFX (для классов ODBC) или функции DFX (для классов DAO) для каждого члена данных в вашем наборе записей.

Функции обмена полями записей передают данные каждый раз, когда платформа вызывает `DoFieldExchange` или `DoBulkFieldExchange`. Каждая функция передает определенный тип данных.

Дополнительные сведения об использовании этих функций см. в статьях [Обмен полями записей: принцип работы RFX (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Для столбцов данных с динамической привязкой можно самостоятельно вызвать функции RFX и DFX, как описано в статьях [Набор записей. Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Кроме того, можно написать собственные подпрограммы RFX и DFX, как описано в техническом примечании [43](../../mfc/tn043-rfx-routines.md) (для ODBC) и техническом примечании [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (для DAO).

На примере функций RFX и Bulk RFX, как они отображаются в функциях `DoFieldExchange` и `DoBulkFieldExchange` функциях, см. [RFX_Text](#rfx_text) и #rfx_text_bulk RFX_Text_Bulk. Функции DFX очень похожи на функции RFX.

### <a name="rfx-functions-odbc"></a>Функции RFX (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|Передает массивы байтов типа [CByteArray](cbytearray-class.md).|
|[RFX_Bool](#rfx_bool)|Передает логический тип данных.|
|[RFX_Byte](#rfx_byte)|Передает один байт данных.|
|[RFX_Date](#rfx_date)|Передача данных о времени и датах с помощью [CTime](../../atl-mfc-shared/reference/ctime-class.md) или TIMESTAMP_STRUCT.|
|[RFX_Double](#rfx_double)|Передает данные двойной точности с плавающей запятой.|
|[RFX_Int](#rfx_int)|Передает целочисленные данные.|
|[RFX_Long](#rfx_long)|Передает длинные целые данные.|
|[RFX_LongBinary](#rfx_longbinary)|Передает данные больших двоичных объектов (BLOB) с объектом класса [CLongBinary](clongbinary-class.md) .|
|[RFX_Single](#rfx_single)|Передает данные с плавающей запятой.|
|[RFX_Text](#rfx_text)|Передает строковые данные.|

### <a name="bulk-rfx-functions-odbc"></a>Функции Bulk RFX (ODBC)

|||
|-|-|
|[RFX_Binary_Bulk](#rfx_binary_bulk)|Передает массивы байтов данных.|
|[RFX_Bool_Bulk](#rfx_bool_bulk)|Передает массивы логических данных.|
|[RFX_Byte_Bulk](#rfx_byte_bulk)|Передает массивы отдельных байтов.|
|[RFX_Date_Bulk](#rfx_date_bulk)|Передает массивы данных типа TIMESTAMP_STRUCT.|
|[RFX_Double_Bulk](#rfx_double_bulk)|Передает массивы данных двойной точности с плавающей запятой.|
|[RFX_Int_Bulk](#rfx_int_bulk)|Передает массивы целочисленных данных.|
|[RFX_Long_Bulk](#rfx_long_bulk)|Передает массивы длинных целых данных.|
|[RFX_Single_Bulk](#rfx_single_bulk)|Передает массивы данных с плавающей запятой.|
|[RFX_Text_Bulk](#rfx_text_bulk)|Передает массивы данных типа LPSTR.|

### <a name="dfx-functions-dao"></a>Функции DFX (DAO)

|||
|-|-|
|[DFX_Binary](#dfx_binary)|Передает массивы байтов типа [CByteArray](cbytearray-class.md).|
|[DFX_Bool](#dfx_bool)|Передает логический тип данных.|
|[DFX_Byte](#dfx_byte)|Передает один байт данных.|
|[DFX_Currency](#dfx_currency)|Передает данные денежных единиц типа [COleCurrency](colecurrency-class.md).|
|[DFX_DateTime](#dfx_datetime)|Передает данные даты и времени типа [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md).|
|[DFX_Double](#dfx_double)|Передает данные двойной точности с плавающей запятой.|
|[DFX_Long](#dfx_long)|Передает длинные целые данные.|
|[DFX_LongBinary](#dfx_longbinary)|Передает данные больших двоичных объектов (BLOB) с объектом класса `CLongBinary` . Для DAO рекомендуется использовать [DFX_Binary](#dfx_binary) .|
|[DFX_Short](#dfx_short)|Передает короткие целые данные.|
|[DFX_Single](#dfx_single)|Передает данные с плавающей запятой.|
|[DFX_Text](#dfx_text)|Передает строковые данные.|

=============================================

## <a name="rfx_binary"></a><a name="rfx_binary"></a>RFX_Binary

Передача массивов байтов между полевыми данными `CRecordset` объекта и столбцов записи на источнике данных типа ODBC SQL_BINARY, SQL_VARBINARY или SQL_LONGVARBINARY.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа [CByteArray](cbytearray-class.md)взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*nMaxДлина*<br/>
Максимально допустимая длина передаваемых строк или массива. Значение по умолчанию *nMaxLength* составляет 255. Правовые значения от 1 до INT_MAX. Платформа выделяет такое количество места для данных. Для наилучшей производительности передайте значение, достаточно большое, чтобы вместить самый большой элемент данных, который вы ожидаете.

### <a name="remarks"></a>Remarks

Данные в источнике данных этих типов `CByteArray` отображались в тип е-евразийого набора.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_bool"></a><a name="rfx_bool"></a>RFX_Bool

Передача данных Boolean между полевыми данными `CRecordset` объекта и столбцов записи об источнике данных типа ODBC SQL_BIT.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа BOOL взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_byte"></a><a name="rfx_byte"></a>RFX_Byte

Передача отдельных байтов между `CRecordset` полевыми данными объекта и столбцов записи на источнике данных типа ODBC SQL_TINYINT.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа BYTE берется из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_date"></a><a name="rfx_date"></a>RFX_Date

Передача `CTime` или TIMESTAMP_STRUCT данных между `CRecordset` полевыми данными объекта и столбцов записи об источнике данных типа ODBC SQL_DATE, SQL_TIME или SQL_TIMESTAMP.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   CTime& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   TIMESTAMP_STRUCT& value);

void RFX_Date(
   CFieldExchange* pFX,
   const char* szName,
   COleDateTime& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных; значение, подносивесебя. Различные версии функции принимают различные типы данных для значения:

Первая версия функции содержит ссылку на объект [CTime.](../../atl-mfc-shared/reference/ctime-class.md) Для переноса из рекордного уровня в источник данных это значение взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

Вторая версия функции содержит ссылку на структуру. `TIMESTAMP_STRUCT` Вы должны настроить эту структуру самостоятельно до вызова. Для этой версии не доступно ни поддержка обмена диалоговыми данными (DDX), ни поддержка мастера кода. Третья версия функции работает аналогично первой версии, за исключением того, что она принимает ссылку на объект [COleDateTime.](../../atl-mfc-shared/reference/coledatetime-class.md)

### <a name="remarks"></a>Remarks

Версия `CTime` функции накладывает накладные расходы на некоторые промежуточные обработки и имеет несколько ограниченный диапазон. Если вы обнаружите, что любой из этих факторов слишком ограничен, используйте вторую версию функции. Но обратите внимание на отсутствие мастера кода и поддержки DDX и требование, что вы создали структуру самостоятельно.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_double"></a><a name="rfx_double"></a>RFX_Double

Передача данных **двойного плавания** между `CRecordset` полевыми данными объекта и столбцов записи на источнике данных типа ODBC SQL_DOUBLE.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных **значение, двойного**типа, взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_int"></a><a name="rfx_int"></a>RFX_Int

Передача неослоедных данных `CRecordset` между полевыми данными объекта и столбцов записи об источнике данных типа ODBC SQL_SMALLINT.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа **int**взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_long"></a><a name="rfx_long"></a>RFX_Long

Передача длинных целых данных между `CRecordset` полевыми данными объекта и столбцов записи об источнике данных типа ODBC SQL_INTEGER.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в исходный исход данных значение типа **длиной**берется из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_longbinary"></a><a name="rfx_longbinary"></a>RFX_LongBinary

Передача двоичных данных крупного объекта (BLOB) с `CRecordset` помощью класса [CLongBinary](clongbinary-class.md) между полевыми членами данных объекта и столбцов записи на источнике данных типа ODBC SQL_LONGVARBINARY или SQL_LONGVARCHAR.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник `CLongBinary`данных значение типа берется из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_single"></a><a name="rfx_single"></a>RFX_Single

Передача данных о плавающей точке `CRecordset` между полевыми данными объекта и столбцов записи на источник еданных типа ODBC SQL_REAL.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение, **поплавок**типа взято из указанного члена данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_text"></a><a name="rfx_text"></a>RFX_Text

Передача `CString` данных между полевыми данными `CRecordset` объекта и столбцов записи об источнике данных типа ODBC SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL или SQL_NUMERIC.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса. `CFieldExchange` Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник `CString`данных значение типа берется из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*nMaxДлина*<br/>
Максимально допустимая длина передаваемых строк или массива. Значение по умолчанию *nMaxLength* составляет 255. Правовые значения от 1 до INT_MAX). Платформа выделяет такое количество места для данных. Для наилучшей производительности передайте значение, достаточно большое, чтобы вместить самый большой элемент данных, который вы ожидаете.

*nColumnType*<br/>
Используется в основном для параметров. Цель с указанием типа данных параметра. Тип — это тип данных ODBC **формы SQL_XXX.**

*nScale*<br/>
Определяет шкалу значений типа ODBC SQL_DECIMAL или SQL_NUMERIC. *nScale* полезен только при настройке значений параметров. Для получения дополнительной информации смотрите тему "Точность, масштаб, длина и размер дисплея" в приложении D *справочника программиста ODBC SDK*.

### <a name="remarks"></a>Remarks

Данные в источнике данных всех этих типов `CString` отображается в и из в наборе записей.

### <a name="example"></a>Пример

Этот пример показывает `RFX_Text`несколько вызовов . Обратите внимание также `CFieldExchange::SetFieldType`на два вызова . Для параметров необходимо написать `SetFieldType` вызов и его вызов RFX. Вызов выходного столбца и связанные с ним вызовы RFX обычно записываются мастером кода.

```cpp
void CCustomer::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   // Macros such as RFX_Text() and RFX_Int() are dependent on the
   // type of the member variable, not the type of the field in the database.
   // ODBC will try to automatically convert the column value to the requested type
   RFX_Long(pFX, _T("[CustomerID]"), m_CustomerID);
   RFX_Text(pFX, _T("[ContactFirstName]"), m_ContactFirstName);
   RFX_Text(pFX, _T("[PostalCode]"), m_PostalCode);
   RFX_Text(pFX, _T("[L_Name]"), m_L_Name);
   RFX_Long(pFX, _T("[BillingID]"), m_BillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_binary_bulk"></a><a name="rfx_binary_bulk"></a>RFX_Binary_Bulk

Перевод нескольких строк данных байта из столбца источника данных ODBC в соответствующий массив в объекте, полученном. `CRecordset`

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgByteVals*<br/>
Указатель на массив значений BYTE. Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывают *prgByteVals.* Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

*nMaxДлина*<br/>
Максимальная допустимая длина значений, хранящихся в массиве, указывается *на prgByteVals.* Чтобы гарантировать, что данные не будут усечены, передайте значение, достаточно большое для размещения самого большого элемента данных, который вы ожидаете.

### <a name="remarks"></a>Remarks

Столбец источника данных может иметь тип SQL_BINARY, SQL_VARBINARY или SQL_LONGVARBINARY ODBC. Набор записей должен определить полевой член данных указателя типа на BYTE.

Если вы инициализируете *prgByteVals* и *prgLengths* к NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Для того, чтобы сделать свой рекордный упорядочить, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Смотрите [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_bool_bulk"></a><a name="rfx_bool_bulk"></a>RFX_Bool_Bulk

Передача нескольких строк данных Boolean из столбца источника данных ODBC в соответствующий массив в объекте, полученном. `CRecordset`

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgBoolVals*<br/>
Указатель на массив значений BOOL. Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывает *prgBoolVals.* Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

### <a name="remarks"></a>Remarks

Столбец источника данных должен иметь тип SQL_BIT ODBC. Набор записей должен определить полевой член данных указателя типа на BOOL.

Если вы инициализируете *prgBoolVals* и *prgLengths* к NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Чтобы обновить набор записей, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Смотрите [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_byte_bulk"></a><a name="rfx_byte_bulk"></a>RFX_Byte_Bulk

Перевод нескольких строк одиночных байтов из столбца источника данных `CRecordset`ODBC в соответствующий массив в объекте, полученном.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgByteVals*<br/>
Указатель на массив значений BYTE. Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывают *prgByteVals.* Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

### <a name="remarks"></a>Remarks

Столбец источника данных должен иметь тип SQL_TINYINT ODBC. Набор записей должен определить полевой член данных указателя типа на BYTE.

Если вы инициализируете *prgByteVals* и *prgLengths* к NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Чтобы обновить набор записей, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Смотрите [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_date_bulk"></a><a name="rfx_date_bulk"></a>RFX_Date_Bulk

Перевод нескольких строк данных TIMESTAMP_STRUCT из столбца источника данных ODBC в соответствующий массив в объекте, полученном. `CRecordset`

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgTSVals*<br/>
Указатель на массив TIMESTAMP_STRUCT значений. Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей. Для получения дополнительной информации о типе данных TIMESTAMP_STRUCT, смотрите тему "C типы данных" в приложении D *от справки программиста ODBC SDK*.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывают *prgTSVals.* Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

### <a name="remarks"></a>Remarks

Столбец источника данных может иметь тип SQL_DATE, SQL_TIME или SQL_TIMESTAMP ODBC. Набор записей должен определить полевой член данных указателя типа TIMESTAMP_STRUCT.

Если вы инициализируете *prgTSVals* и *prgLengths* к NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Чтобы обновить набор записей, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Смотрите [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_double_bulk"></a><a name="rfx_double_bulk"></a>RFX_Double_Bulk

Передача нескольких рядов данных с двойной точностью с плавающей точки из столбца `CRecordset`источника данных ODBC в соответствующий массив в объекте, полученном.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgDblVals*<br/>
Указатель на массив **двойных** значений. Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывает *prgBlVals.* Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

### <a name="remarks"></a>Remarks

Столбец источника данных должен иметь тип SQL_DOUBLE ODBC. Запись должна определить, что член данных поля указателя типа **удвоится.**

Если вы инициализируете *prgDblVals* и *prgLengths* к NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Чтобы обновить набор записей, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Смотрите [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_int_bulk"></a><a name="rfx_int_bulk"></a>RFX_Int_Bulk

Передача неослоедных данных `CRecordset` между полевыми данными объекта и столбцов записи об источнике данных типа ODBC SQL_SMALLINT.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации об операциях `CFieldExchange` объект может указать, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md)

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа **int**взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

### <a name="example"></a>Пример

Смотрите [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_long_bulk"></a><a name="rfx_long_bulk"></a>RFX_Long_Bulk

Перевод нескольких рядов длинных целых данных из столбца источника данных `CRecordset`ODBC в соответствующий массив в объекте, полученном.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgLongVals*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывает *prgLongVals.* Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

### <a name="remarks"></a>Remarks

Столбец источника данных должен иметь тип SQL_INTEGER ODBC. Запись должна определить полевой член данных указателя типа к **длинному.**

Если вы инициализируете *prgLongVals* и *prgLengths* к NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Чтобы обновить набор записей, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Смотрите [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_single_bulk"></a><a name="rfx_single_bulk"></a>RFX_Single_Bulk

Передача нескольких рядов данных плавающей точки из столбца источника данных `CRecordset`ODBC в соответствующий массив в объекте, полученном.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgFltVals*<br/>
Указатель на массив значений **поплавка.** Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывает *prgFltVals.* Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

### <a name="remarks"></a>Remarks

Столбец источника данных должен иметь тип SQL_REAL ODBC. Запись должна определить, что для плавания полевой член данных указателя типа **должен находиться**в поле.

Если вы инициализируете *prgFltVals* и *prgLengths* к NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Чтобы обновить набор записей, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Смотрите [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_text_bulk"></a><a name="rfx_text_bulk"></a>RFX_Text_Bulk

Перевод нескольких строк данных символов из столбца источника данных `CRecordset`ODBC в соответствующий массив в объекте, полученном.

### <a name="syntax"></a>Синтаксис

```cpp
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](cfieldexchange-class.md) Этот объект содержит информацию для определения контекста для каждого вызова функции. Для получения дополнительной информации, см. статью [Запись Поле обмена: Как RFX работает](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Название столбца данных.

*prgStrVals*<br/>
Указатель на массив значений LPSTR. Этот массив будет хранить данные, которые будут передаваться из источника данных в набор записей. Обратите внимание, что в текущей версии ODBC эти значения не могут быть Unicode.

*prgДлины*<br/>
Указатель на массив длинных целых чихов. Этот массив будет хранить длину байтов каждого значения в массиве, на который указывают *prgStrVals.* Эта длина исключает символ нулевого прекращения. Обратите внимание, что значение SQL_NULL_DATA будет храниться, если соответствующий элемент данных содержит значение Null. Для получения более подробной информации `SQLBindCol` см. функцию ODBC API в *справочнике программиста ODBC SDK.*

*nMaxДлина*<br/>
Максимальная допустимая длина значений, хранящихся в массиве, указывается *на prgStrVals,* включая символ нулевого прекращения. Чтобы гарантировать, что данные не будут усечены, передайте значение, достаточно большое для размещения самого большого элемента данных, который вы ожидаете.

### <a name="remarks"></a>Remarks

Столбец источника данных может иметь тип SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL или SQL_NUMERIC ODBC. Набор записей должен определить полевых данных члена типа LPSTR.

Если вы инициализируете *prgStrVals* и *prgLengths* в NULL, то массивы, на которые они указывают, будут выделены автоматически, с размерами, равными размеру рядового.

> [!NOTE]
> Массовый обмен поля записи только передает данные из источника данных на объект записи. Чтобы обновить набор записей, необходимо использовать функцию `SQLSetPos`ODBC API.

Для получения дополнительной информации смотрите статьи [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [запись поле обмена (RFX)](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Вы должны вручную писать `DoBulkFieldExchange` вызовы в переопределение. В этом примере `RFX_Text_Bulk`отображается вызов к, а также вызов к, `RFX_Long_Bulk`для передачи данных. Этим вызовам предшествует звонок в [CFieldExchange::SetFieldType](cfieldexchange-class.md#setfieldtype). Обратите внимание, что для параметров необходимо вызывать функции RFX вместо функций Bulk RFX.

```cpp
void CMultiCustomer::DoBulkFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Long_Bulk(pFX, _T("[CustomerID]"), &m_pCustomerID, &m_pcCustomerID);
   RFX_Text_Bulk(pFX, _T("[ContactFirstName]"), &m_pContactFirstName, &m_pcContactFirstName, 50);
   RFX_Text_Bulk(pFX, _T("[PostalCode]"), &m_pPostalCode, &m_pcPostalCode, 50);
   RFX_Text_Bulk(pFX, _T("[L_Name]"), &m_pL_Name, &m_pcL_Name, 50);
   RFX_Long_Bulk(pFX, _T("[BillingID]"), &m_pBillingID, &m_pcBillingID);

   pFX->SetFieldType(CFieldExchange::inputParam);
   RFX_Text(pFX, _T("Param"), m_strParam);
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="dfx_binary"></a><a name="dfx_binary"></a>DFX_Binary

Передача массивов байтов между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа [CByteArray](cbytearray-class.md)взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*nPreAllocSize*<br/>
Рамки предраспределяет этот объем памяти. Если ваши данные больше, фреймворк будет выделять больше места по мере необходимости. Для повышения производительности установите этот размер до достаточно большого значения, чтобы предотвратить перераспределения. Размер по умолчанию определяется в AFXDAO. H файл как AFX_DAO_BINARY_DEFAULT_SIZE.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_DISABLE_FIELD_CACHE, не используется двойной буферизации, и вы должны позвонить [SetFieldDirty](cdaorecordset-class.md#setfielddirty) и [SetFieldNull](cdaorecordset-class.md#setfieldnull) себя. Другое возможное значение, AFX_DAO_ENABLE_FIELD_CACHE, использует двойное буферизирование, и вам не придется делать дополнительную работу, чтобы отметить поля грязные или Null. По причинам производительности и памяти избегайте этого значения, если ваши двоичные данные не являются относительно небольшими.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными для всех полей по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_BYTES типа в DAO и вветром [CByteArray](cbytearray-class.md) в наборе рекордов.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_bool"></a><a name="dfx_bool"></a>DFX_Bool

Передача данных Boolean между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа BOOL взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_BOOL типа в DAO и типом BOOL в рекордном наборе.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_byte"></a><a name="dfx_byte"></a>DFX_Byte

Передача отдельных байтов между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа BYTE берется из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_BYTES типа в DAO и ввезлом BYTE в рекордном наборе.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_currency"></a><a name="dfx_currency"></a>DFX_Currency

Передача валютных данных между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для передачи из рекордного уровня в источник данных это значение взято из указанного участника данных типа [COleCurrency.](colecurrency-class.md) Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между типом DAO_CURRENCY в DAO и вветром [COleCurrency](colecurrency-class.md) в рекордном наборе.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_datetime"></a><a name="dfx_datetime"></a>DFX_DateTime

Передача данных о времени и дате между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Функция содержит ссылку на объект [COleDateTime.](../../atl-mfc-shared/reference/coledatetime-class.md) Для переноса из рекордного уровня в источник данных это значение взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_DATE типа в DAO и [типом COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) в рекордном наборе.

> [!NOTE]
> `COleDateTime`заменяет [CTime](../../atl-mfc-shared/reference/ctime-class.md) и TIMESTAMP_STRUCT для этой цели в классах DAO. `CTime`и TIMESTAMP_STRUCT по-прежнему используются для классов доступа к данным на основе ODBC.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_double"></a><a name="dfx_double"></a>DFX_Double

Передача данных **двойного плавания** между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных **значение, двойного**типа, взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между типом DAO_R8 в DAO и ввеком **двойного плавания** в рекордном наборе.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_long"></a><a name="dfx_long"></a>DFX_Long

Передача длинных целых данных между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в исходный исход данных значение типа **длиной**берется из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_I4 типа в DAO и **введите долго** в наборе рекордов.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_longbinary"></a><a name="dfx_longbinary"></a>DFX_LongBinary

**Важно** Вместо этой функции рекомендуется использовать [DFX_Binary.](#dfx_binary)

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для передачи из рекордного уровня в источник данных значение типа [CLongBinary](clongbinary-class.md)взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwPreAllocSize*<br/>
Рамки предраспределяет этот объем памяти. Если ваши данные больше, фреймворк будет выделять больше места по мере необходимости. Для повышения производительности установите этот размер до достаточно большого значения, чтобы предотвратить перераспределения.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DISABLE_FIELD_CACHE, не используется двойное буферизация. Другим возможным значением является AFX_DAO_ENABLE_FIELD_CACHE. Использует двойное буферизация, и вам не придется делать дополнительную работу, чтобы отметить поля грязными или Null. По причинам производительности и памяти избегайте этого значения, если ваши двоичные данные не являются относительно небольшими.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

`DFX_LongBinary`предусмотрена совместимость с классами MFC ODBC. Функция `DFX_LongBinary` передает данные большого двоичного объекта (BLOB) с помощью класса `CLongBinary` между элементами данных поля объекта [CDaoRecordset](cdaorecordset-class.md) и столбцами записи в источнике данных. Данные отображались между типом DAO_BYTES в DAO и вветром [CLongBinary](clongbinary-class.md) в рекордном наборе.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_short"></a><a name="dfx_short"></a>DFX_Short

Передача коротких рядовых данных между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение, **краткое**типа, взято из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_I2 типа в DAO и **короткими** в записи.

> [!NOTE]
> `DFX_Short`эквивалентно [RFX_Int](#rfx_int) для классов на основе ODBC.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_single"></a><a name="dfx_single"></a>DFX_Single

Передача данных о плавающей точке между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение, **поплавок**типа взято из указанного члена данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны `SetFieldDirty` `SetFieldNull` позвонить и себе.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_R4 типа в DAO и **введите плавающий в** наборе рекордов.

### <a name="example"></a>Пример

Смотрите [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_text"></a><a name="dfx_text"></a>DFX_Text

Передача `CString` данных между полевыми данными объекта [CDaoRecordset](cdaorecordset-class.md) и столбцов записи на источнике данных.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию для определения контекста для каждого вызова функции.

*szName*<br/>
Название столбца данных.

*value*<br/>
Значение, хранящееся в указанном участнике данных - значение, подаваемые. Для переноса из рекордного уровня в источник данных значение типа [CString](../../atl-mfc-shared/reference/cstringt-class.md)берется из указанного участника данных. Для передачи от источника данных к рекорду значение сохраняется в указанном участнике данных.

*nPreAllocSize*<br/>
Рамки предраспределяет этот объем памяти. Если ваши данные больше, фреймворк будет выделять больше места по мере необходимости. Для повышения производительности установите этот размер до достаточно большого значения, чтобы предотвратить перераспределения.

*dwBindOptions*<br/>
Опция, которая позволяет воспользоваться механизмом двойного буферизации MFC для обнаружения измененных полей записей. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, используется двойное буферизация. Другое возможное значение AFX_DAO_DISABLE_FIELD_CACHE. Если вы укажете это значение, MFC не проверяет это поле. Вы должны позвонить [SetFieldDirty](cdaorecordset-class.md#setfielddirty) и [SetFieldNull](cdaorecordset-class.md#setfieldnull) себя.

> [!NOTE]
> Вы можете контролировать, являются ли данные двойными буферизированными по умолчанию, установив [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Remarks

Данные отображались между DAO_CHAR типа в DAO (или, если символ _UNICODE определен, DAO_WCHAR) и вветром [CString](../../atl-mfc-shared/reference/cstringt-class.md) в наборе записей.  n

### <a name="example"></a>Пример

Этот пример показывает `DFX_Text`несколько вызовов . Обратите внимание также на два звонка на [CDaoFieldExchange::SetFieldType](cdaofieldexchange-class.md#setfieldtype). Вы должны написать `SetFieldType` первый звонок и его **dFX** вызова. Второй вызов и связанные с ним **вызовы DFX** обычно записываются мастером кода, сгенерированным классом.

```cpp
void CCustSet::DoFieldExchange(CDaoFieldExchange* pFX)
{
   pFX->SetFieldType(CDaoFieldExchange::param);
   DFX_Text(pFX, _T("Param"), m_strParam);
   pFX->SetFieldType(CDaoFieldExchange::outputColumn);
   DFX_Short(pFX, _T("EmployeeID"), m_EmployeeID);
   DFX_Text(pFX, _T("LastName"), m_LastName);
   DFX_Short(pFX, _T("Age"), m_Age);
   DFX_DateTime(pFX, _T("hire_date"), m_hire_date);
   DFX_DateTime(pFX, _T("termination_date"), m_termination_date);

   CDaoRecordset::DoFieldExchange(pFX);
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)
