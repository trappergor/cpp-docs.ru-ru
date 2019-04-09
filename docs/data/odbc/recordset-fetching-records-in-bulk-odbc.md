---
title: Набор записей. Пакетная выборка строк (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- bulk row fetching, implementing
- ODBC recordsets, bulk row fetching
- bulk record field exchange
- bulk row fetching
- bulk RFX functions
- recordsets, bulk row fetching
- DoBulkFieldExchange method
- fetching ODBC records in bulk
- RFX (ODBC), bulk
- rowsets, bulk row fetching
- RFX (ODBC), bulk row fetching
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
ms.openlocfilehash: 2fdcbf18fcb0d97ba7b2a39aa9bbbd79e65a4112
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027770"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Набор записей. Пакетная выборка строк (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Класс `CRecordset` обеспечивает поддержку выборка строк, что означает, что несколько записей можно извлечь за один раз во время одной выборки, а не получение одной записи за раз из источника данных. Вы можете реализовать выборка строк только в производном `CRecordset` класса. Процесс передачи данных из источника данных в объекте набора записей, называется блочный обмен полей записей (Bulk RFX). Обратите внимание, что если вы не используете выборка строк в `CRecordset`-производного класса, данные передаются через обмен полями записей (RFX). Дополнительные сведения см. в разделе [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).

Содержание раздела:

- [Как CRecordset поддерживает массовое получение строк](#_core_how_crecordset_supports_bulk_row_fetching).

- [Особые рекомендации при использовании пакетная выборка строк](#_core_special_considerations).

- [Как реализовать блочный обмен полей записей](#_core_how_to_implement_bulk_record_field_exchange).

##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> Как CRecordset поддерживает получение строк

Перед открытием объекта набора записей, можно определить размер набора строк с `SetRowsetSize` функция-член. Размер набора строк указывает, сколько записей должно быть извлечено за одну операцию выборки. При реализации выборка строк, размер набора строк по умолчанию — 25. Если выборка строк не реализована, размер набора строк остается равным 1.

После установки размера набора строк вызовите [откройте](../../mfc/reference/crecordset-class.md#open) функция-член. Здесь необходимо указать `CRecordset::useMultiRowFetch` параметр *dwOptions* параметр выборка строк. Кроме того, можно задать `CRecordset::userAllocMultiRowBuffers` параметр. Механизм обмена полями записей массового использует массивов для хранения нескольких строк данных, полученных во время выборки. Буферы хранения могут быть выделены автоматически платформой, или они могут быть добавлены вручную. Указание `CRecordset::userAllocMultiRowBuffers` вариант означает, что вы сделаете выделение.

В следующей таблице перечислены функции-члены, предоставляемые `CRecordset` для поддержки выборка строк.

|Функция-член|Описание|
|---------------------|-----------------|
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|Виртуальная функция, которая обрабатывает все ошибки, возникающие во время выборки.|
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Реализует блочный обмен полей записей. Вызывается автоматически для передачи нескольких строк данных из источника данных в объект набора записей.|
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Извлекает текущее значение размера набора строк.|
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Сообщает, сколько строк, фактически были получены после операции выборки. В большинстве случаев это размер набора строк, если не была сделана выборка неполного набора строк.|
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Возвращает состояние выборки для конкретной строки в набор строк.|
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Обновляет данные и состояние конкретной строки в набор строк.|
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|Перемещает курсор к конкретной строки в набор строк.|
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Виртуальная функция, которая изменяет параметр размера набора строк, соответствующие заданному значению.|

##  <a name="_core_special_considerations"></a> Особые замечания

Несмотря на то, что выборка строк повышается производительность, некоторые функции работают по-разному. Прежде чем выборка строк, учитывайте следующее:

- Платформа автоматически вызывает `DoBulkFieldExchange` функция-член для передачи данных из источника данных в объекте набора записей. Тем не менее данные не передаются из набора записей в источнике данных. Вызов `AddNew`, `Edit`, `Delete`, или `Update` результатов функции элемент в утверждение, вызвавшее сбой. Несмотря на то что `CRecordset` в настоящее время не предоставляет механизм для обновления пакетов строк данных, можно создавать собственные функции с помощью функции ODBC API `SQLSetPos`. Дополнительные сведения о `SQLSetPos`, см. в разделе *Справочник по программированию ODBC SDK* в документации MSDN.

- Функции-члены `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty`, и `SetFieldNull` не может использоваться для наборов записей, выборка строк. Тем не менее, можно вызвать `GetRowStatus` вместо `IsDeleted`, и `GetODBCFieldInfo` вместо `IsFieldNullable`.

- `Move` Операций перемещают набор записей в наборе строк. Например предположим, что открыть набор записей, 100 записей с начальным размером набора строк из 10. `Open` Извлекает строки с 1 по 10, с текущей записью, располагается в строке 1. Вызов `MoveNext` извлекает следующего набора строк, а не следующей строки. Этот набор строк состоит из строки с 11 по 20, при этом текущая запись располагается в строке 11. Обратите внимание, что `MoveNext` и `Move( 1 )` не эквивалентны, при массовой выборке строк реализации. `Move( 1 )` Извлекает набор строк, который начинается 1 строка из текущей записи. В этом примере вызов `Move( 1 )` после вызова метода `Open` извлекает набор строк, состоящий из строки 2 — 11, при этом текущая запись располагается в строке 2. Дополнительные сведения см. в разделе [переместить](../../mfc/reference/crecordset-class.md#move) функция-член.

- В отличие от обмен полями записей мастера не поддерживают блочный обмен полей записей. Это означает, что необходимо вручную объявить члены-поля данных и вручную переопределить `DoBulkFieldExchange` , вызовы функций Bulk RFX. Дополнительные сведения см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md) в *Справочник по библиотеке классов*.

##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> Как реализовать блочный обмен полей записей

Блочный обмен полей записей передает набор строк данных из источника данных в объект набора записей. Функции Bulk RFX использование массивов для хранения этих данных, а также массивов для хранения длины каждого элемента данных в наборе строк. В определении класса необходимо определить члены-поля данных как указатели для доступа к массивам данных. Кроме того необходимо определить набор указателей для доступа к массивам длин. Членов данных параметров не должны быть объявлены как указатели; объявление членов данных параметров при использовании блочный обмен полей записей — это так же, как их объявления, при использовании обмен полями записей. Ниже приведен простой пример:

```cpp
class MultiRowSet : public CRecordset
{
public:
   // Field/Param Data
      // field data members
      long* m_rgID;
      LPSTR m_rgName;

      // pointers for the lengths
      // of the field data
      long* m_rgIDLengths;
      long* m_rgNameLengths;

      // input parameter data member
      CString m_strNameParam;

   .
   .
   .
}
```

Можно выделить эти буферы хранилища вручную или иметь средой выполнения распределения. Чтобы выделить буферы самостоятельно, необходимо указать `CRecordset::userAllocMultiRowBuffers` параметр *dwOptions* параметр в `Open` функция-член. Не забудьте задать размеры массивов по крайней мере равно размеру набора строк. Если вы хотите иметь средой выполнения распределения, необходимо инициализировать указатели NULL. Обычно это делается в конструкторе объекта набора записей:

```cpp
MultiRowSet::MultiRowSet( CDatabase* pDB )
   : CRecordset( pDB )
{
   m_rgID = NULL;
   m_rgName = NULL;
   m_rgIDLengths = NULL;
   m_rgNameLengths = NULL;
   m_strNameParam = "";

   m_nFields = 2;
   m_nParams = 1;

   .
   .
   .
}
```

Наконец, необходимо переопределить `DoBulkFieldExchange` функция-член. Для элементов данных полей вызова функций Bulk RFX; для элементов данных параметров вызовите функции RFX. Если набор записей открыт, передавая инструкцию SQL или хранимую процедуру `Open`, порядок, в котором производятся вызовы функций Bulk RFX должен соответствовать порядку столбцов в наборе записей; аналогичным образом, порядок RFX вызывает для параметров должен соответствовать порядком параметров в инструкции SQL или хранимой процедуры.

```cpp
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )
{
   // call the Bulk RFX functions
   // for field data members
   pFX->SetFieldType( CFieldExchange::outputColumn );
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),
                  &m_rgID, &m_rgIDLengths );
   RFX_Text_Bulk( pFX, _T( "[colName]" ),
                  &m_rgName, &m_rgNameLengths, 30 );

   // call the RFX functions for
   // for parameter data members
   pFX->SetFieldType( CFieldExchange::inputParam );
   RFX_Text( pFX, "NameParam", m_strNameParam );
}
```

> [!NOTE]
>  Необходимо вызвать `Close` функция-член перед производного `CRecordset` класс выходит за пределы области. Это гарантирует, что память, выделенную средой освобождаются. Это рекомендуется всегда явно вызвать `Close`, независимо от того, реализуется ли пакетная выборка строк.

Дополнительные сведения о обмен полями записей (RFX), см. в разделе [обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Дополнительные сведения об использовании параметров см. в разделе [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) и [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

## <a name="see-also"></a>См. также

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

