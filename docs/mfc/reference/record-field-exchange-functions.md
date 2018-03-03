---
title: "Функции обмена полями записи | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 94491a2df64017ea381377af8518414e80130d6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-functions"></a>Функции обмена данными полями записей
В этом разделе перечислены обмен полями записей (RFX Bulk RFX и DFX) функции, которые используются для автоматизации передачи данных между объектом набора записей и источником данных и выполнения других операций с данными.  
  
 При использовании классов на основе ODBC и реализации массовой выборки строк необходимо вручную переопределить функцию-член `DoBulkFieldExchange` `CRecordset` путем вызова функций Bulk RFX для каждого элемента данных, соответствующего столбцу источника данных.  
  
 Если в классах на основе ODBC массовая выборка строк не реализована или если вы используете классы на основе DAO, мастер ClassWizard переопределит функцию-член `DoFieldExchange` `CRecordset` или `CDaoRecordset` путем вызова функций RFX (для классов ODBC) или функций DFX (для классов DAO) для каждого элемента данных поля в наборе записей.  
  
 Функции обмена полями записей передают данные каждый раз, когда платформа вызывает `DoFieldExchange` или `DoBulkFieldExchange`. Каждая функция передает определенный тип данных.  
  
 Дополнительные сведения об использовании этих функций см. в статьях [Обмен полями записей: принцип работы RFX (ODBC)](../../data/odbc/record-field-exchange-how-rfx-works.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Для столбцов данных с динамической привязкой можно самостоятельно вызвать функции RFX и DFX, как описано в статьях [Набор записей. Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). Кроме того, можно написать собственные подпрограммы RFX и DFX, как описано в техническом примечании [43](../../mfc/tn043-rfx-routines.md) (для ODBC) и техническом примечании [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) (для DAO).  
  
 Пример функций RFX и Bulk RFX функции, как они отображаются в `DoFieldExchange` и `DoBulkFieldExchange` функции, в разделе [RFX_Text](#rfx_text) и rfx_text_bulk # [RFX_Text_Bulk]). Функции DFX очень похожи на функции RFX.  
  
### <a name="rfx-functions-odbc"></a>Функции RFX (ODBC)  
  
|||  
|-|-|  
|[RFX_Binary](#rfx_binary)|Передает массивы байтов типа [CByteArray](cbytearray-class.md).|  
|[RFX_Bool](#rfx_bool)|Передает логический тип данных.|  
|[RFX_Byte](#rfx_byte)|Передает один байт данных.|  
|[RFX_Date](#rfx_date)|Передает значения времени и даты с помощью [CTime](../../atl-mfc-shared/reference/ctime-class.md) или **TIMESTAMP_STRUCT**.|  
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
|[RFX_Date_Bulk](#rfx_date_bulk)|Передает массивы данных типа **TIMESTAMP_STRUCT**.|  
|[RFX_Double_Bulk](#rfx_double_bulk)|Передает массивы данных двойной точности с плавающей запятой.|  
|[RFX_Int_Bulk](#rfx_int_bulk)|Передает массивы целочисленных данных.|  
|[RFX_Long_Bulk](#rfx_long_bulk)|Передает массивы длинных целых данных.|  
|[RFX_Single_Bulk](#rfx_single_bulk)|Передает массивы данных с плавающей запятой.|  
|[RFX_Text_Bulk](#rfx_text_bulk)|Передает массивы данных типа **LPSTR**.|  
  
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
Передает массивы байтов между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_BINARY**, **SQL_VARBINARY**, или **SQL_ LONGVARBINARY**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Binary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CByteArray& value,  
   int nMaxLength = 255);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа [CByteArray](cbytearray-class.md), берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `nMaxLength`  
 Максимально допустимая длина строки или массива, передаваемый. Значение по умолчанию `nMaxLength` — 255. Допустимые значения: от 1 до `INT_MAX`. Платформа выделяет этот объем пространства для данных. Для повышения производительности рекомендуется передайте достаточно велик для хранения наибольший элемент данных, который предполагается, что значение.  
  
### <a name="remarks"></a>Примечания  
 Сопоставления данных в источнике данных из этих типов в тип и из `CByteArray` в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_bool"></a>  RFX_Bool
Передает логический тип данных между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_BIT**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Bool(  
   CFieldExchange* pFX,  
   const char* szName,  
   BOOL& value);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **BOOL**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_byte"></a>  RFX_Byte
Передает один байт между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_TINYINT**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Byte(  
   CFieldExchange* pFX,  
   const char* szName,  
   BYTE& value);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **БАЙТОВ**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_date"></a>  RFX_Date
Передача `CTime` или **TIMESTAMP_STRUCT** данных между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_DATE**, **SQL_TIME**, или **SQL_TIMESTAMP**.  
  
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
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в элементе указанные данные; значение должно быть передано. Различные версии функции принимать различные типы данных для значения:  
  
 Первая версия функции, принимающей ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта. При передаче из набора записей с источником данных это значение берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 Вторая версия функции, принимающей ссылку на **TIMESTAMP_STRUCT** структуры. Необходимо настроить эту структуру самостоятельно до вызова метода. Поддерживают ни обмен данными (диалоговых окон DDX) и поддержка мастера кода доступны для этой версии. Третья версия функции работают схожим образом с первой версией, за исключением того, что он принимает ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 `CTime` Версии функции снижение некоторые промежуточной обработки и некоторой степени ограничены диапазоном значений. Если любой из этих факторов слишком ограничивающим, используйте второй версии функции. Но Обратите внимание, отсутствие поддержка DDX и мастер создания кода и требование, которое можно настроить структуру самостоятельно.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_double"></a>  RFX_Double
Передача **double float** данных между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_DOUBLE**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Double(  
   CFieldExchange* pFX,  
   const char* szName,  
   double& value);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **двойные**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_int"></a>  RFX_Int
Передает целочисленные данные между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа `int`, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_long"></a>  RFX_Long
Передает данные в длинное целое число между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_INTEGER**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Long(  
   CFieldExchange* pFX,  
   const char* szName,  
   LONG&   
value );  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **длинные**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
## <a name="rfx_longbinary"></a>  RFX_LongBinary
Передает данные больших двоичных объектов (BLOB) с помощью класса [CLongBinary](clongbinary-class.md) между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_LONGVARBINARY**или **SQL_LONGVARCHAR**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_LongBinary(  
   CFieldExchange* pFX,  
   const char* szName,  
   CLongBinary& value);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа `CLongBinary`, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_single"></a>  RFX_Single
Передача данных с плавающей запятой между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_REAL**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Single(  
   CFieldExchange* pFX,  
   const char* szName,  
   float& value);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **float**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  

## <a name="rfx_text"></a>  RFX_Text
Передача `CString` данных между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_ VARCHAR**, **SQL_DECIMAL**, или **SQL_NUMERIC**.  
  
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
 `pFX`  
 Указатель на объект класса `CFieldExchange`. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа `CString`, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `nMaxLength`  
 Максимально допустимая длина строки или массива, передаваемый. Значение по умолчанию `nMaxLength` — 255. Допустимые значения: от 1 до `INT_MAX`). Платформа выделяет этот объем пространства для данных. Для повышения производительности рекомендуется передайте достаточно велик для хранения наибольший элемент данных, который предполагается, что значение.  
  
 *nColumnType*  
 Используется главным образом для параметров. Целое число, указывающее тип данных параметра. Тип является типом данных ODBC формы **SQL_XXX**.  
  
 `nScale`  
 Задает масштаб для значения типа ODBC **SQL_DECIMAL** или **SQL_NUMERIC**. `nScale`полезно только при задании значения параметров. Дополнительные сведения см. в разделе «Точность, масштаб, длину и отображаемый размер» в приложении D *справочнике программиста ODBC SDK*.  
  
### <a name="remarks"></a>Примечания  
 Сопоставления данных в источнике данных всех этих типов в / из `CString` в наборе записей.  
  
### <a name="example"></a>Пример  
 В этом примере показано несколько вызовов `RFX_Text`. Обратите внимание также два вызова `CFieldExchange::SetFieldType`. Для параметров необходимо написать вызов `SetFieldType` и его вызов RFX. Выходной столбец и его связанные вызовов RFX обычно записываются мастером код.  
  
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
Передает несколько строк данных байтов из столбца источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
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
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgByteVals`  
 Указатель на массив **БАЙТОВ** значения. Этот массив хранения данных для передачи из источника данных в набор записей.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgByteVals`. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
 `nMaxLength`  
 Максимально допустимая длина значений, хранящихся в массиве, на который указывает `prgByteVals`. Чтобы убедиться, что данные не будут усечены, передайте значение достаточно велик для хранения самого большого элемента данных предполагается, что.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных может иметь тип ODBC **SQL_BINARY**, **SQL_VARBINARY**, или **SQL_LONGVARBINARY**. Набор записей необходимо определить тип указателя на член данных поля **БАЙТОВ**.  
  
 Если инициализировать `prgByteVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_bool_bulk"></a>  RFX_Bool_Bulk
Передает несколько строк данных Boolean из столбца источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Bool_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL** prgBoolVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgBoolVals`  
 Указатель на массив **BOOL** значения. Этот массив хранения данных для передачи из источника данных в набор записей.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgBoolVals`. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных должны иметь тип ODBC **SQL_BIT**. Набор записей необходимо определить тип указателя на член данных поля **BOOL**.  
  
 Если инициализировать `prgBoolVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_byte_bulk"></a>  RFX_Byte_Bulk
Передает несколько строк один байт из столбца источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Byte_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE** prgByteVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgByteVals`  
 Указатель на массив **БАЙТОВ** значения. Этот массив хранения данных для передачи из источника данных в набор записей.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgByteVals`. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных должны иметь тип ODBC **SQL_TINYINT**. Набор записей необходимо определить тип указателя на член данных поля **БАЙТОВ**.  
  
 Если инициализировать `prgByteVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
## <a name="rfx_date_bulk"></a>  RFX_Date_Bulk
Передача нескольких строк **TIMESTAMP_STRUCT** данные из столбцов источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Date_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   TIMESTAMP_STRUCT** prgTSVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgTSVals`  
 Указатель на массив **TIMESTAMP_STRUCT** значения. Этот массив хранения данных для передачи из источника данных в набор записей. Дополнительные сведения о **TIMESTAMP_STRUCT** тип данных, см. в разделе «Типы данных C» в приложении D *справочнике программиста ODBC SDK*.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgTSVals`. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных может иметь тип ODBC **SQL_DATE**, **SQL_TIME**, или **SQL_TIMESTAMP**. Набор записей необходимо определить тип указателя на член данных поля **TIMESTAMP_STRUCT**.  
  
 Если инициализировать `prgTSVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_double_bulk"></a>  RFX_Double_Bulk
Передает несколько строк двойной точности с плавающей запятой данных из столбца источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Double_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   double** prgDblVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgDblVals`  
 Указатель на массив **двойные** значения. Этот массив хранения данных для передачи из источника данных в набор записей.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgDblVals`. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных должны иметь тип ODBC **SQL_DOUBLE**. Набор записей необходимо определить тип указателя на член данных поля **двойные**.  
  
 Если инициализировать `prgDblVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_int_bulk"></a>  RFX_Int_Bulk
Передает целочисленные данные между элементами данных полей `CRecordset` объектов и столбцы записи в источнике данных ODBC типа **SQL_SMALLINT**.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Int(  
   CFieldExchange* pFX,  
   const char* szName,  
   int& value);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [разделе](cfieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения об операциях `CFieldExchange` объекта можно указать, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа `int`, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text](#rfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_long_bulk"></a>  RFX_Long_Bulk
Передает несколько строк данных типа long integer из столбца источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Long_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   long** prgLongVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgLongVals`  
 Указатель на массив длинных целых чисел. Этот массив хранения данных для передачи из источника данных в набор записей.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgLongVals`. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных должны иметь тип ODBC **SQL_INTEGER**. Набор записей необходимо определить тип указателя на член данных поля **длинные**.  
  
 Если инициализировать `prgLongVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  

## <a name="rfx_single_bulk"></a>  RFX_Single_Bulk
Передает несколько строк данных с плавающей запятой из столбца источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void RFX_Single_Bulk(  
   CFieldExchange* pFX,  
   LPCTSTR szName,  
   float** prgFltVals,  
   long** prgLengths);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgFltVals`  
 Указатель на массив **float** значения. Этот массив хранения данных для передачи из источника данных в набор записей.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgFltVals`. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных должны иметь тип ODBC **SQL_REAL**. Набор записей необходимо определить тип указателя на член данных поля **float**.  
  
 Если инициализировать `prgFltVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 В разделе [RFX_Text_Bulk](#rfx_text_bulk).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  

## <a name="rfx_text_bulk"></a>  RFX_Text_Bulk
Передает несколько строк символьных данных из столбца источника данных ODBC на соответствующий массив в `CRecordset`-производного объекта.  
  
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
 `pFX`  
 Указатель на [разделе](cfieldexchange-class.md) объекта. Этот объект содержит сведения для определения контекста для каждого вызова функции. Дополнительные сведения см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 `szName`  
 Имя столбца данных.  
  
 `prgStrVals`  
 Указатель на массив **LPSTR** значения. Этот массив хранения данных для передачи из источника данных в набор записей. Обратите внимание, что в текущей версии ODBC, эти значения не может быть Юникода.  
  
 `prgLengths`  
 Указатель на массив длинных целых чисел. Этот массив будет сохранять длину в байтах для каждого значения в массиве, на который указывает `prgStrVals`. Эту длину исключает нулевой символ. Обратите внимание, что значение **SQL_NULL_DATA** будет сохранен в том случае, если соответствующий элемент данных содержит значение Null. Дополнительные сведения см. в описании функции API-интерфейса ODBC **SQLBindCol** в *справочнике программиста ODBC SDK*.  
  
 `nMaxLength`  
 Максимально допустимая длина значений, хранящихся в массиве, на который указывает `prgStrVals`, включая символ завершения null. Чтобы убедиться, что данные не будут усечены, передайте значение достаточно велик для хранения самого большого элемента данных предполагается, что.  
  
### <a name="remarks"></a>Примечания  
 Столбцы источника данных может иметь тип ODBC **SQL_LONGVARCHAR**, **SQL_CHAR**, **SQL_VARCHAR**, **SQL_DECIMAL**, или **SQL_NUMERIC**. Набор записей необходимо определить элемент поля данных типа **LPSTR**.  
  
 Если инициализировать `prgStrVals` и `prgLengths` для **NULL**, а затем массивы, они указывают выделяется автоматически, с размерами, равно размеру набора строк.  
  
> [!NOTE]
>  Блочный обмен полей записей передает только данные из источника данных объекта набора записей. Чтобы сделать возможно обновление набора записей, необходимо использовать функцию ODBC API **SQLSetPos**.  
  
 Дополнительные сведения см. в статьях [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) и [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
### <a name="example"></a>Пример  
 Необходимо вручную записать вызовы вашей `DoBulkFieldExchange` переопределения. В этом примере показан вызов `RFX_Text_Bulk`, а также вызов `RFX_Long_Bulk`, для передачи данных. Эти вызовы перед вызовом [CFieldExchange::SetFieldType](CFieldExchange::SetFieldType.md). Обратите внимание, что для параметров, необходимо вызвать функции RFX вместо функций Bulk RFX.  
  
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
Передает массивы байтов между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
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
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа [CByteArray](cbytearray-class.md), берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `nPreAllocSize`  
 Платформа предварительно размещает объемом памяти. Если размер данных, платформа будет выделить больше места, при необходимости. Для повышения производительности присвоено значение, достаточное для предотвращения перераспределениями этот размер. Размер по умолчанию определяется в AFXDAO. H-файл как **AFX_DAO_BINARY_DEFAULT_SIZE**.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_DISABLE_FIELD_CACHE`, не двойной буферизации использования и необходимо вызвать [SetFieldDirty](cdaorecordset-class.md#setfielddirty) и [метод SetFieldNull](cdaorecordset-class.md#setfieldnull) самостоятельно. Другие возможные значения `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации и вы не должны выполнить дополнительную работу, чтобы пометить поля "грязный" или Null. По производительности и памяти причинам не это значение, если только двоичные данные относительно невелико.  
  
> [!NOTE]
>  Можно управлять ли данных double в буфер для всех полей по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_BYTES** DAO и типу [CByteArray](cbytearray-class.md) в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  

## <a name="dfx_bool"></a>  DFX_Bool
Передает логический тип данных между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_Bool(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BOOL& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **BOOL**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_BOOL** DAO и типу **BOOL** в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

## <a name="dfx_byte"></a>  DFX_Byte
Передает один байт между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_Byte(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   BYTE& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **БАЙТОВ**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_BYTES** DAO и типу **БАЙТОВ** в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

## <a name="dfx_currency"></a>  DFX_Currency
Передает данные денежных единиц между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_Currency(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleCurrency& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора записей с источником данных это значение берется из указанных данных члена типа [COleCurrency](colecurrency-class.md). Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_CURRENCY** DAO и типу [COleCurrency](colecurrency-class.md) в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

## <a name="dfx_datetime"></a>  DFX_DateTime
Передает данные даты и времени между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_DateTime(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   COleDateTime& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. Эта функция принимает ссылку на [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объекта. При передаче из набора записей с источником данных это значение берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_DATE** DAO и типу [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) в наборе записей.  
  
> [!NOTE]
>  `COleDateTime`заменяет [CTime](../../atl-mfc-shared/reference/ctime-class.md) и **TIMESTAMP_STRUCT** в классы DAO для этой цели. `CTime`и **TIMESTAMP_STRUCT** все еще используется для классов доступа к данным на основе ODBC.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

## <a name="dfx_double"></a>  DFX_Double
Передача **double float** данных между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_Double(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   double& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **двойные**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_R8** DAO и типу **double float** в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

## <a name="dfx_long"></a>  DFX_Long
Передает данные в длинное целое число между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_Long(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   long& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **длинные**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_I4** DAO и типу **длинные** в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  

## <a name="dfx_longbinary"></a>  DFX_LongBinary
**Важные** , рекомендуется использовать [DFX_Binary](#dfx_binary) вместо этой функции.  
  
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
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа [CLongBinary](clongbinary-class.md), берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 *dwPreAllocSize*  
 Платформа предварительно размещает объемом памяти. Если размер данных, платформа будет выделить больше места, при необходимости. Для повышения производительности присвоено значение, достаточное для предотвращения перераспределениями этот размер.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию **AFX_DISABLE_FIELD_CACHE**, не используйте двойной буферизации. Возможное значение — `AFX_DAO_ENABLE_FIELD_CACHE`. Использование двойной буферизации и вы не должны выполнить дополнительные действия, чтобы пометить поля "грязный" или Null. По производительности и памяти причинам не это значение, если только двоичные данные относительно невелико.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 `DFX_LongBinary`обеспечивает совместимость с использованием классов MFC ODBC. `DFX_LongBinary` Функция передает данные больших двоичных-объектов (BLOB) с помощью класса `CLongBinary` между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных. Сопоставления между типом данных **DAO_BYTES** DAO и типу [CLongBinary](clongbinary-class.md) в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

## <a name="dfx_short"></a>  DFX_Short
Передает короткие целые данные между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_Short(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   short& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **короткие**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_I2** DAO и типу **короткие** в наборе записей.  
  
> [!NOTE]
>  `DFX_Short`эквивалентно [RFX_Int](#rfx_int) для классов на основе ODBC.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  

## <a name="dfx_single"></a>  DFX_Single
Передача данных с плавающей запятой между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
### <a name="syntax"></a>Синтаксис  
  
```
void AFXAPI DFX_Single(  
   CDaoFieldExchange* pFX,  
   LPCTSTR szName,  
   float& value,  
   DWORD dwBindOptions = AFX_DAO_ENABLE_FIELD_CACHE);  
```  
  
### <a name="parameters"></a>Параметры  
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа **float**, берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать `SetFieldDirty` и `SetFieldNull` самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_R4** DAO и типу **float** в наборе записей.  
  
### <a name="example"></a>Пример  
 В разделе [DFX_Text](#dfx_text).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  

## <a name="dfx_text"></a>  DFX_Text
Передача `CString` данных между элементами данных полей [CDaoRecordset](cdaorecordset-class.md) объектов и столбцы записи в источнике данных.  
  
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
 `pFX`  
 Указатель на объект класса [CDaoFieldExchange](cdaofieldexchange-class.md). Этот объект содержит сведения для определения контекста для каждого вызова функции.  
  
 `szName`  
 Имя столбца данных.  
  
 *значение*  
 Значение, хранящееся в указанные данные элемента, значение должно быть передано. При передаче из набора данных к источнику данных, значение типа [CString](../../atl-mfc-shared/reference/cstringt-class.md), берется из заданного элемента данных. Для передачи из источника данных в набор записей значение, хранящееся в заданный элемент данных.  
  
 `nPreAllocSize`  
 Платформа предварительно размещает объемом памяти. Если размер данных, платформа будет выделить больше места, при необходимости. Для повышения производительности присвоено значение, достаточное для предотвращения перераспределениями этот размер.  
  
 `dwBindOptions`  
 Параметр, который позволяет воспользоваться преимуществами MFC двойной буферизации механизм определения полей набора записей, которые были изменены. Значение по умолчанию `AFX_DAO_ENABLE_FIELD_CACHE`, использует двойной буферизации. Возможное значение — `AFX_DAO_DISABLE_FIELD_CACHE`. Если это значение указано, MFC не выполняет проверки на это поле не. Необходимо вызвать [SetFieldDirty](cdaorecordset-class.md#setfielddirty) и [метод SetFieldNull](cdaorecordset-class.md#setfieldnull) самостоятельно.  
  
> [!NOTE]
>  Можно управлять ли данные двойной буферизации по умолчанию, задав [CDaoRecordset::m_bCheckCacheForDirtyFields](cdaorecordset-class.md#m_bcheckcachefordirtyfields).  
  
### <a name="remarks"></a>Примечания  
 Сопоставления между типом данных **DAO_CHAR** в DAO (или, если символ **_UNICODE** определен, **DAO_WCHAR**) и тип [CString](../../atl-mfc-shared/reference/cstringt-class.md) в набор записей.  n
  
### <a name="example"></a>Пример  
 В этом примере показано несколько вызовов `DFX_Text`. Обратите внимание также два вызова [CDaoFieldExchange::SetFieldType](cdaofieldexchange-class.md#setfieldtype). Необходимо написать первый вызов `SetFieldType` и его **DFX** вызова. Второй вызов и связанный с ним **DFX** вызовы обычно записываются при помощи мастера код, созданный класс.  
  
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
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](crecordset-class.md#dofieldexchange)   
 [CRecordset::DoBulkFieldExchange](crecordset-class.md#dobulkfieldexchange)   
 [CDaoRecordset::DoFieldExchange](cdaorecordset-class.md#dofieldexchange)

