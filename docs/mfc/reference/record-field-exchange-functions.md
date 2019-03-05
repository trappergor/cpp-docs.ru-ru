---
title: Функции обмена данными полями записей
ms.date: 11/04/2016
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
ms.openlocfilehash: 865c67b88c37e32ef33fa410ef178b81b7a6ecac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297077"
---
# <a name="record-field-exchange-functions"></a>Функции обмена данными полями записей

В этом разделе перечислены обмен полями записей (RFX Bulk RFX и DFX) функции, которые используются для автоматизации передачи данных между объектом набора записей и источником данных и выполнения других операций с данными.

При использовании классов на основе ODBC и реализации массовой выборки строк необходимо вручную переопределить функцию-член `DoBulkFieldExchange` `CRecordset` путем вызова функций Bulk RFX для каждого элемента данных, соответствующего столбцу источника данных.

Если в классах на основе ODBC массовая выборка строк не реализована или если вы используете классы на основе DAO, мастер ClassWizard переопределит функцию-член `DoFieldExchange` `CRecordset` или `CDaoRecordset` путем вызова функций RFX (для классов ODBC) или функций DFX (для классов DAO) для каждого элемента данных поля в наборе записей.

Функции обмена полями записей передают данные каждый раз, когда платформа вызывает `DoFieldExchange` или `DoBulkFieldExchange`. Каждая функция передает определенный тип данных.

Дополнительные сведения об использовании этих функций см. в статьях [обмен полями записей: Принцип работы RFX (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Дополнительные сведения о массовой выборке строк см. в статье [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Для столбцов данных с динамической привязкой, можно также вызвать функции RFX и DFX, как описано в статьях [набор записей: Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Кроме того, можно написать собственные подпрограммы RFX и DFX, как описано в техническом примечании [43](../../mfc/tn043-rfx-routines.md) (для ODBC) и техническом примечании [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (для DAO).

Пример функций RFX и Bulk RFX функции, как они отображаются в `DoFieldExchange` и `DoBulkFieldExchange` функции, см. в разделе [RFX_Text](#rfx_text) и rfx_text_bulk # [RFX_Text_Bulk]). Функции DFX очень похожи на функции RFX.

### <a name="rfx-functions-odbc"></a>Функции RFX (ODBC)

|||
|-|-|
|[RFX_Binary](#rfx_binary)|Передает массивы байтов типа [CByteArray](cbytearray-class.md).|
|[RFX_Bool](#rfx_bool)|Передает логический тип данных.|
|[RFX_Byte](#rfx_byte)|Передает один байт данных.|
|[RFX_Date](#rfx_date)|Передает значения времени и даты с помощью [CTime](../../atl-mfc-shared/reference/ctime-class.md) или TIMESTAMP_STRUCT.|
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

## <a name="rfx_binary"></a>  RFX_Binary

Передает массивы байтов между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_BINARY, SQL_VARBINARY или SQL_LONGVARBINARY.

### <a name="syntax"></a>Синтаксис

```
void RFX_Binary(
   CFieldExchange* pFX,
   const char* szName,
   CByteArray& value,
   int nMaxLength = 255);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип [CByteArray](cbytearray-class.md), берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*nMaxLength*<br/>
Максимально допустимая длина строки или массива, передаваемый. Значение по умолчанию *nMaxLength* составляет 255. Допустимые значения: от 1 до INT_MAX. Платформа выделяет этот объем пространства для данных. Для наилучшей производительности передайте значение достаточно велик для хранения наибольшего элемента данных, ожидаемых.

### <a name="remarks"></a>Примечания

Сопоставления данных в источнике данных из этих типов в тип и из `CByteArray` в наборе записей.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_bool"></a>  RFX_Bool

Передает логический тип данных между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_BIT.

### <a name="syntax"></a>Синтаксис

```
void RFX_Bool(
   CFieldExchange* pFX,
   const char* szName,
   BOOL& value);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей в источнике данных значение, тип BOOL, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_byte"></a>  RFX_Byte

Передает один байт между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_TINYINT.

### <a name="syntax"></a>Синтаксис

```
void RFX_Byte(
   CFieldExchange* pFX,
   const char* szName,
   BYTE& value);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей в источнике данных значение типа BYTE, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_date"></a>  RFX_Date

Передача `CTime` или TIMESTAMP_STRUCT данных между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_DATE, SQL_TIME или SQL_TIMESTAMP.

### <a name="syntax"></a>Синтаксис

```
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

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные; значение должно быть передано. Различные версии функции, принимающих данные разных типов для значения:

Первая версия функции принимает ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта. При передаче из набора записей в источнике данных это значение берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

Вторая версия функции принимает ссылку на `TIMESTAMP_STRUCT` структуры. Необходимо настроить эту структуру самостоятельно до вызова. Поддерживают ни обмен данными диалоговых окон (DDX) и поддержка мастера кода доступна для этой версии. Третья версия функция работает подобно элементу первой версии, за исключением того, что он принимает ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта.

### <a name="remarks"></a>Примечания

`CTime` Версию функции влечет дополнительную нагрузку в некоторых промежуточной обработки и имеет широкий ряд ограничений. Если любой из этих факторов слишком ограничивающим, используйте второй версии функции. Но Обратите внимание, отсутствие мастера кода и поддержка DDX и требование, которое можно настроить структуру самостоятельно.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_double"></a>  RFX_Double

Передача **double float** данных между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_DOUBLE.

### <a name="syntax"></a>Синтаксис

```
void RFX_Double(
   CFieldExchange* pFX,
   const char* szName,
   double& value);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **двойные**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_int"></a>  RFX_Int

Передает целочисленные данные между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_SMALLINT.

### <a name="syntax"></a>Синтаксис

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **int**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_long"></a>  RFX_Long

Передает данные длинное целое число между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_INTEGER.

### <a name="syntax"></a>Синтаксис

```
void RFX_Long(
   CFieldExchange* pFX,
   const char* szName,
   LONG&
value );
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **long**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_longbinary"></a>  RFX_LongBinary

Передает данные больших двоичных объектов (BLOB), с помощью класса [CLongBinary](clongbinary-class.md) между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_LONGVARBINARY и SQL_LONGVARCHAR.

### <a name="syntax"></a>Синтаксис

```
void RFX_LongBinary(
   CFieldExchange* pFX,
   const char* szName,
   CLongBinary& value);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип `CLongBinary`, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_single"></a>  RFX_Single

Передача данных с плавающей запятой между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_REAL.

### <a name="syntax"></a>Синтаксис

```
void RFX_Single(
   CFieldExchange* pFX,
   const char* szName,
   float& value);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **float**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_text"></a>  RFX_Text

Передача `CString` данных между элементами данных полей `CRecordset` объекта и записи в источнике данных ODBC типа SQL_LONGVARCHAR, SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL или SQL_NUMERIC.

### <a name="syntax"></a>Синтаксис

```
void RFX_Text(
   CFieldExchange* pFX,
   const char* szName,
   CString& value,
   int nMaxLength = 255,
   int nColumnType = SQL_VARCHAR,
   short nScale = 0);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса `CFieldExchange`. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип `CString`, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*nMaxLength*<br/>
Максимально допустимая длина строки или массива, передаваемый. Значение по умолчанию *nMaxLength* составляет 255. Допустимые значения: от 1 до INT_MAX). Платформа выделяет этот объем пространства для данных. Для наилучшей производительности передайте значение достаточно велик для хранения наибольшего элемента данных, ожидаемых.

*nColumnType*<br/>
Используется главным образом для параметров. Целое число, указывающее тип данных параметра. Тип является типом данных ODBC в форме **SQL_XXX**.

*nScale*<br/>
Задает масштаб для значения типа ODBC SQL_DECIMAL или SQL_NUMERIC. *nScale* полезен только при задании значения параметров. Дополнительные сведения см. в разделе «Точность, масштаб, длину и отображаемый размер» в приложении D *Справочник по программированию ODBC SDK*.

### <a name="remarks"></a>Примечания

Сопоставления данных в источнике данных все эти типы и обратно `CString` в наборе записей.

### <a name="example"></a>Пример

В этом примере показано несколько вызовов `RFX_Text`. Обратите внимание, что также два вызова `CFieldExchange::SetFieldType`. Для параметров необходимо написать вызов `SetFieldType` и его вызов RFX. Столбец выходных данных и его связанных вызовов RFX обычно записываются мастером код.

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

## <a name="rfx_binary_bulk"></a>  RFX_Binary_Bulk

Передает несколько строк байтов данных из столбца источника данных ODBC на соответствующий массив в `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Binary_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgByteVals*<br/>
Указатель на массив БАЙТОВЫХ значений. Этот массив будут храниться данные будут передаваться из источника данных в набор записей.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgByteVals*. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

*nMaxLength*<br/>
Максимально допустимая длина значений, хранящихся в массиве, на которые указывают *prgByteVals*. Чтобы убедиться, что данные не будут усечены, передайте значение достаточно велик для хранения наибольшего элемента данных, ожидаемых.

### <a name="remarks"></a>Примечания

Столбцы источника данных могут иметь типа ODBC SQL_BINARY, SQL_VARBINARY или SQL_LONGVARBINARY. Набор записей необходимо определить элемент данных поля, тип указателя БАЙТОВ.

Если инициализировать *prgByteVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

См. в разделе [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_bool_bulk"></a>  RFX_Bool_Bulk

Передает несколько строк данных Boolean из столбца источника данных ODBC в соответствующий массив `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Bool_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BOOL** prgBoolVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgBoolVals*<br/>
Указатель на массив значений типа BOOL. Этот массив будут храниться данные будут передаваться из источника данных в набор записей.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgBoolVals*. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

### <a name="remarks"></a>Примечания

Столбцы источника данных должны иметь типа ODBC SQL_BIT. Набор записей необходимо определить элемент поля данных типа pointer в BOOL.

Если инициализировать *prgBoolVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

См. в разделе [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_byte_bulk"></a>  RFX_Byte_Bulk

Передает несколько строк отдельных байтов из столбца источника данных ODBC в соответствующий массив `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Byte_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   BYTE** prgByteVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgByteVals*<br/>
Указатель на массив БАЙТОВЫХ значений. Этот массив будут храниться данные будут передаваться из источника данных в набор записей.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgByteVals*. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

### <a name="remarks"></a>Примечания

Столбцы источника данных должны иметь типа ODBC SQL_TINYINT. Набор записей необходимо определить элемент данных поля, тип указателя БАЙТОВ.

Если инициализировать *prgByteVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

См. в разделе [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_date_bulk"></a>  RFX_Date_Bulk

Передает несколько строк данных TIMESTAMP_STRUCT из столбца источника данных ODBC в соответствующий массив `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Date_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   TIMESTAMP_STRUCT** prgTSVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgTSVals*<br/>
Указатель на массив значений TIMESTAMP_STRUCT. Этот массив будут храниться данные будут передаваться из источника данных в набор записей. Дополнительные сведения о типе данных TIMESTAMP_STRUCT см. в разделе «Типы данных C» в приложении D *Справочник по программированию ODBC SDK*.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgTSVals*. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

### <a name="remarks"></a>Примечания

Столбцы источника данных могут иметь типа ODBC, SQL_DATE, SQL_TIME или SQL_TIMESTAMP. Набор записей необходимо определить TIMESTAMP_STRUCT элемента данных поля, тип указателя.

Если инициализировать *prgTSVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

См. в разделе [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_double_bulk"></a>  RFX_Double_Bulk

Передает несколько строк двойной точности с плавающей запятой данных из столбца источника данных ODBC на соответствующий массив в `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Double_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   double** prgDblVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgDblVals*<br/>
Указатель на массив **двойные** значения. Этот массив будут храниться данные будут передаваться из источника данных в набор записей.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgDblVals*. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

### <a name="remarks"></a>Примечания

Столбцы источника данных должно иметь тип ODBC SQL_DOUBLE. Набор записей необходимо определить тип указателя на член данных поля **двойные**.

Если инициализировать *prgDblVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

См. в разделе [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_int_bulk"></a>  RFX_Int_Bulk

Передает целочисленные данные между элементами данных полей `CRecordset` объекта и столбцы записи в источнике данных ODBC типа SQL_SMALLINT.

### <a name="syntax"></a>Синтаксис

```
void RFX_Int(
   CFieldExchange* pFX,
   const char* szName,
   int& value);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CFieldExchange](cfieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объект может задавать, см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **int**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

### <a name="example"></a>Пример

См. в разделе [RFX_Text](#rfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_long_bulk"></a>  RFX_Long_Bulk

Передает несколько строк данных длинное целое число из столбца источника данных ODBC в соответствующий массив `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Long_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   long** prgLongVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgLongVals*<br/>
Указатель на массив длинных целых чисел. Этот массив будут храниться данные будут передаваться из источника данных в набор записей.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgLongVals*. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

### <a name="remarks"></a>Примечания

Столбцы источника данных должны иметь типа ODBC SQL_INTEGER. Набор записей необходимо определить тип указателя на член данных поля **long**.

Если инициализировать *prgLongVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

См. в разделе [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_single_bulk"></a>  RFX_Single_Bulk

Передает несколько строк данных с плавающей запятой из столбца источника данных ODBC в соответствующий массив `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Single_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   float** prgFltVals,
   long** prgLengths);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgFltVals*<br/>
Указатель на массив **float** значения. Этот массив будут храниться данные будут передаваться из источника данных в набор записей.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgFltVals*. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

### <a name="remarks"></a>Примечания

Столбцы источника данных должны иметь типа ODBC SQL_REAL. Набор записей необходимо определить тип указателя на член данных поля **float**.

Если инициализировать *prgFltVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

См. в разделе [RFX_Text_Bulk](#rfx_text_bulk).

### <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="rfx_text_bulk"></a>  RFX_Text_Bulk

Передает несколько строк, символьных данных из столбца источника данных ODBC в соответствующий массив `CRecordset`-объект, производный от.

### <a name="syntax"></a>Синтаксис

```
void RFX_Text_Bulk(
   CFieldExchange* pFX,
   LPCTSTR szName,
   LPSTR* prgStrVals,
   long** prgLengths,
   int nMaxLength);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на [CFieldExchange](cfieldexchange-class.md) объекта. Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

*szName*<br/>
Имя столбца данных.

*prgStrVals*<br/>
Указатель на массив значений LPSTR. Этот массив будут храниться данные будут передаваться из источника данных в набор записей. Обратите внимание, что в текущей версии ODBC, эти значения не могут быть Юникода.

*prgLengths*<br/>
Указатель на массив длинных целых чисел. Этот массив будет хранить длина в байтах для каждого значения в массиве, на которые указывают *prgStrVals*. Эта длина исключает последний нулевой символ. Обратите внимание на то, что будет храниться значение SQL_NULL_DATA, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в разделе функции ODBC API `SQLBindCol` в *Справочник по программированию ODBC SDK*.

*nMaxLength*<br/>
Максимально допустимая длина значений, хранящихся в массиве, на которые указывают *prgStrVals*, включая последний нулевой символ. Чтобы убедиться, что данные не будут усечены, передайте значение достаточно велик для хранения наибольшего элемента данных, ожидаемых.

### <a name="remarks"></a>Примечания

Столбцы источника данных могут иметь типа ODBC SQL_LONGVARCHAR SQL_CHAR, SQL_VARCHAR, SQL_DECIMAL и SQL_NUMERIC. Набор записей необходимо определить поля данных членом типа LPSTR.

Если инициализировать *prgStrVals* и *prgLengths* значение NULL, а затем массивы, они указывают, выделяется автоматически, с размером, равным размеру набора строк.

> [!NOTE]
>  Блочный обмен полей записей только передает данные из источника данных в объекте набора записей. Чтобы сделать обновляемые набора записей, необходимо использовать функцию ODBC API `SQLSetPos`.

Дополнительные сведения см. в статьях [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md).

### <a name="example"></a>Пример

Необходимо вручную написать вызовы вашей `DoBulkFieldExchange` переопределить. В этом примере показан вызов `RFX_Text_Bulk`, а также вызов `RFX_Long_Bulk`, для передачи данных. Эти вызовы перед вызовом [CFieldExchange::SetFieldType](CFieldExchange::SetFieldType.md). Обратите внимание, что для параметров, необходимо вызвать функции RFX вместо функций Bulk RFX.

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

## <a name="dfx_binary"></a>  DFX_Binary

Передает массивы байтов между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Binary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CByteArray& value,
   int nPreAllocSize = AFX_DAO_BINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип [CByteArray](cbytearray-class.md), берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*nPreAllocSize*<br/>
Платформа выделяет этот объем памяти. Если размер данных, платформа будет выделено больше места, при необходимости. Для повышения производительности задавайте этот размер достаточно большой, чтобы предотвратить перераспределения значение. Размер по умолчанию определяется в AFXDAO. Файл H как AFX_DAO_BINARY_DEFAULT_SIZE.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_DISABLE_FIELD_CACHE, использует ли двойной буферизации и необходимо вызвать [SetFieldDirty](cdaorecordset-class.md#setfielddirty) и [метод SetFieldNull](cdaorecordset-class.md#setfieldnull) самостоятельно. Еще одно значение, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации, и необходимо выполнить дополнительную работу, чтобы пометить поля "грязной", или значение Null. Для производительности и памяти по причинам не это значение, если только двоичные данные относительно невелико.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию для всех полей, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления между типом DAO_BYTES в DAO и типом данных [CByteArray](cbytearray-class.md) в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_bool"></a>  DFX_Bool

Передает логический тип данных между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Bool(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BOOL& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей в источнике данных значение, тип BOOL, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления данных между типом DAO_BOOL в DAO и типа BOOL в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_byte"></a>  DFX_Byte

Передает один байт между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Byte(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   BYTE& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей в источнике данных значение типа BYTE, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления данных между типом DAO_BYTES в DAO и типа BYTE в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_currency"></a>  DFX_Currency

Передает данные денежных единиц между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Currency(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleCurrency& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей в источнике данных это значение берется из указанных данных члена, типа [COleCurrency](colecurrency-class.md). При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления между типом DAO_CURRENCY в DAO и типом данных [COleCurrency](colecurrency-class.md) в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_datetime"></a>  DFX_DateTime

Передает данные даты и времени между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_DateTime(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   COleDateTime& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. Функция принимает ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта. При передаче из набора записей в источнике данных это значение берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления между типом DAO_DATE в DAO и типом данных [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) в наборе записей.

> [!NOTE]
>  `COleDateTime` заменяет [CTime](../../atl-mfc-shared/reference/ctime-class.md) и TIMESTAMP_STRUCT для этой цели в классы DAO. `CTime` и TIMESTAMP_STRUCT по-прежнему используются для классов доступа к данным на основе ODBC.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_double"></a>  DFX_Double

Передача **double float** данных между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Double(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   double& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **двойные**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления между типом DAO_R8 в DAO и типом данных **double float** в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_long"></a>  DFX_Long

Передает данные длинное целое число между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Long(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   long& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **long**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления между типом DAO_I4 в DAO и типом данных **long** в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_longbinary"></a>  DFX_LongBinary

**Важные** рекомендуется использовать [DFX_Binary](#dfx_binary) вместо этой функции.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_LongBinary(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CLongBinary& value,
   DWORD dwPreAllocSize = AFX_DAO_LONGBINARY_DEFAULT_SIZE,
   DWORD dwBindOptions = 0);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип [CLongBinary](clongbinary-class.md), берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwPreAllocSize*<br/>
Платформа выделяет этот объем памяти. Если размер данных, платформа будет выделено больше места, при необходимости. Для повышения производительности задавайте этот размер достаточно большой, чтобы предотвратить перераспределения значение.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DISABLE_FIELD_CACHE, не используйте двойной буферизации. Еще одно значение — AFX_DAO_ENABLE_FIELD_CACHE. Двойная буферизация использует и вам не нужно выполнить дополнительную работу, чтобы пометить поля "грязной", или значение Null. Для производительности и памяти по причинам не это значение, если только двоичные данные относительно невелико.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

`DFX_LongBinary` предоставляется для совместимости с классами MFC ODBC. `DFX_LongBinary` Функция передает двоичных больших объектов (BLOB) данных, с помощью класса `CLongBinary` между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных. Сопоставления между типом DAO_BYTES в DAO и типом данных [CLongBinary](clongbinary-class.md) в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_short"></a>  DFX_Short

Передает короткие целые данные между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Short(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   short& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **короткие**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления между типом DAO_I2 в DAO и типом данных **короткие** в наборе записей.

> [!NOTE]
>  `DFX_Short` эквивалентно [RFX_Int](#rfx_int) для классов на основе ODBC.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_single"></a>  DFX_Single

Передача данных с плавающей запятой между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и столбцы записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Single(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   float& value,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип **float**, берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Сопоставления между типом DAO_R4 в DAO и типом данных **float** в наборе записей.

### <a name="example"></a>Пример

См. в разделе [DFX_Text](#dfx_text).

### <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="dfx_text"></a>  DFX_Text

Передача `CString` данных между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объекта и записи в источнике данных.

### <a name="syntax"></a>Синтаксис

```
void AFXAPI DFX_Text(
   CDaoFieldExchange* pFX,
   LPCTSTR szName,
   CString& value,
   int nPreAllocSize = AFX_DAO_TEXT_DEFAULT_SIZE,
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);
```

### <a name="parameters"></a>Параметры

*pFX*<br/>
Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит информацию, чтобы определить контекст для каждого вызова функции.

*szName*<br/>
Имя столбца данных.

*value*<br/>
Значение, хранящееся в элементе указанные данные, значение должно быть передано. При передаче из набора записей к источнику данных, значение, тип [CString](../../atl-mfc-shared/reference/cstringt-class.md), берется из заданного элемента данных. При передаче из источника данных в набор записей значение хранится в заданный элемент данных.

*nPreAllocSize*<br/>
Платформа выделяет этот объем памяти. Если размер данных, платформа будет выделено больше места, при необходимости. Для повышения производительности задавайте этот размер достаточно большой, чтобы предотвратить перераспределения значение.

*dwBindOptions*<br/>
Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения поля набора записей, которые были изменены. По умолчанию, AFX_DAO_ENABLE_FIELD_CACHE, использует двойной буферизации. Еще одно значение — AFX_DAO_DISABLE_FIELD_CACHE. Если это значение указано, MFC не проверка этого поля. Необходимо вызвать [SetFieldDirty](cdaorecordset-class.md#setfielddirty) и [метод SetFieldNull](cdaorecordset-class.md#setfieldnull) самостоятельно.

> [!NOTE]
>  Можно управлять, являются ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).

### <a name="remarks"></a>Примечания

Данные сопоставляются между типом DAO_CHAR в DAO (или, если определен символ _UNICODE, DAO_WCHAR) и тип [CString](../../atl-mfc-shared/reference/cstringt-class.md) в наборе записей.  n

### <a name="example"></a>Пример

В этом примере показано несколько вызовов `DFX_Text`. Обратите внимание, что также два вызова [CDaoFieldExchange::SetFieldType](cdaofieldexchange-class.md#setfieldtype). Необходимо написать первый вызов `SetFieldType` и его **DFX** вызова. Второй вызов и связанный с ним **DFX** вызовы обычно записываются с помощью мастера код, созданный класс.

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

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)<br/>
[CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)<br/>
[CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)
