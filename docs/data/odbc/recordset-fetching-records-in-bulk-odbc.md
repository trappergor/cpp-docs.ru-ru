---
title: 'Набор записей: пакетная выборка строк (ODBC)'
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
ms.openlocfilehash: ec4d83481f6335d4c40ffb8f004b617f2ee09c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367029"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Набор записей: пакетная выборка строк (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Класс `CRecordset` обеспечивает поддержку извлечения навалочных строк, что означает, что несколько записей могут быть извлечены одновременно в течение одного привлечения, а не получать одну запись за раз из источника данных. Вы можете реализовать объемный ряд, `CRecordset` извлекающий только в производном классе. Процесс передачи данных из источника данных на объект записи называется объемным обменом полями записей (Bulk RFX). Обратите внимание, что если вы не `CRecordset`используете объемные строки, извлекающиеся в классе, полученных, данные передаются через обмен поля записи (RFX). Для получения дополнительной [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)информации см.

В этом разделе рассматриваются следующие вопросы.

- [Как CRecordset поддерживает объемстроки извлечения](#_core_how_crecordset_supports_bulk_row_fetching).

- [Некоторые специальные соображения при использовании объемного строки извлечения](#_core_special_considerations).

- [Как реализовать объемный обмен поля записи.](#_core_how_to_implement_bulk_record_field_exchange)

## <a name="how-crecordset-supports-bulk-row-fetching"></a><a name="_core_how_crecordset_supports_bulk_row_fetching"></a>Как CRecordset поддерживает массовую строку Fetching

Перед открытием объекта набора записей можно определить `SetRowsetSize` размер строки с функцией участника. Размер строки определяет, сколько записей должно быть извлечено во время одного извлечения. При реализации навалочных строк размер строки составляет 25 строк. Если извлечения объемного ряда не реализованы, размер рядовостается на уровне 1.

После инициализации размера строки позвоните в функцию [Open](../../mfc/reference/crecordset-class.md#open) member. Здесь необходимо указать опцию `CRecordset::useMultiRowFetch` параметра *dwOptions* для реализации навалочных строк извлечения. Вы можете дополнительно `CRecordset::userAllocMultiRowBuffers` установить опцию. Механизм обмена полями навалом записей использует массивы для хранения нескольких строк данных, извлеченных во время извлечения. Эти буферы хранения могут быть автоматически выделены фреймворкой или вы можете распределить их вручную. Указание опции `CRecordset::userAllocMultiRowBuffers` означает, что вы будете выполнять распределение.

В следующей таблице перечислены `CRecordset` функции участника, предоставляемые для поддержки извлечения объемных строк.

|Функция-член|Описание|
|---------------------|-----------------|
|[CheckRowsetОшибка](../../mfc/reference/crecordset-class.md#checkrowseterror)|Виртуальная функция, которая обрабатывает любые ошибки, которые происходят во время извлечения.|
|[ДобалкФилдОбмен](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Реализует объемную биржу полей записей. Вызывается автоматически для передачи нескольких строк данных из источника данных в объект записи.|
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Извлекает текущий параметр для размера рядового набора.|
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Сообщает, сколько строк было получено после данного получения. В большинстве случаев это размер строки, если только не был извлечен неполный набор строк.|
|[ГетРоуСтатусстом](../../mfc/reference/crecordset-class.md#getrowstatus)|Возвращает статус получения для определенной строки в строке.|
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Обновляет данные и состояние определенной строки в строке.|
|[SetRowsetCursorПозиция](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|Перемещает курсор в определенный ряд в пределах рядка.|
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Виртуальная функция, которая изменяет настройку для размера строки на указанное значение.|

## <a name="special-considerations"></a><a name="_core_special_considerations"></a>Специальные соображения

Несмотря на то, что навалочный ряд извлечения является увеличение производительности, некоторые функции работают по-разному. Прежде чем вы решите реализовать объем строки извлечения, рассмотрим следующее:

- Платформа автоматически вызывает `DoBulkFieldExchange` функцию члена для передачи данных из источника данных на объект записи. Однако данные не передаются из рекордного момента обратно в источник данных. Вызов `AddNew`функций `Delete`, `Update` `Edit`или функций участника приводит к неудавому утверждению. Хотя `CRecordset` в настоящее время не предусмотрен механизм обновления объемных строк данных, вы можете `SQLSetPos`написать свои собственные функции с помощью функции ODBC API. Для получения `SQLSetPos`дополнительной информации о , см. *справку программиста ODBC SDK* в документации MSDN.

- Функцияучастника `IsDeleted`, `IsFieldDirty` `IsFieldNull`, `IsFieldNullable` `SetFieldDirty`, `SetFieldNull` , и не может быть использован на записи, которые реализуют объем строки извлечения. Тем не менее, вы `IsDeleted`можете `GetODBCFieldInfo` позвонить `IsFieldNullable` `GetRowStatus` на место, и вместо .

- Операции `Move` перемещают ваш рекорд по строке. Например, предположим, что вы открываете набор записей с 100 записями с первоначальным размером рядов 10. `Open`получает строки от 1 до 10, с текущей записью, расположенной на строке 1. Вызов для `MoveNext` получения следующего строки, а не следующего ряда. Этот ряд состоит из строк с 11 по 20, с текущей записью, расположенной на строке 11. Обратите `MoveNext` внимание, что и `Move( 1 )` не являются эквивалентными, когда объем строки извлечения реализована. `Move( 1 )`получает строку, которая начинается 1 строка из текущей записи. В этом примере `Move( 1 )` `Open` вызов после вызова получает набор строк, состоящий из строк 2 до 11, при этом текущая запись расположена на строке 2. Для получения дополнительной [информации](../../mfc/reference/crecordset-class.md#move) см.

- В отличие от обмена полями записей, мастера не поддерживают обмен поля с объемом записей. Это означает, что вы должны вручную декларировать `DoBulkFieldExchange` членов полевых данных и вручную переопределять, записывая вызовы на функции Bulk RFX. Для получения дополнительной информации смотрите [функции обмена полевыми данными](../../mfc/reference/record-field-exchange-functions.md) в *справочнике библиотеки класса.*

## <a name="how-to-implement-bulk-record-field-exchange"></a><a name="_core_how_to_implement_bulk_record_field_exchange"></a>Как реализовать массовую биржу поля записи

Массовый обмен поля записи передает ряд данных из источника данных на объект записи. Функции Bulk RFX используют массивы для хранения этих данных, а также массивы для хранения длины каждого элемента данных в наборе строк. В определении класса необходимо определить членов полевых данных в качестве указателей для доступа к массивам данных. Кроме того, необходимо определить набор указателей для доступа к массивам длин. Любые участники параметра не должны объявляться указатели; декларирование параметров данных членов при использовании объемного обмена поля записи же, как объявить их при использовании обмена поля записи. Следующий код показывает простой пример:

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

Эти буферы хранения можно распределить вручную, либо посмотреть, как фреймворк, сделать распределение. Чтобы самостоятельно выделить буферы, необходимо `CRecordset::userAllocMultiRowBuffers` указать опцию параметра `Open` *dwOptions* в функции члена. Не забудьте установить размеры массивов по крайней мере равны размеру рядов. Если вы хотите, чтобы фреймворк сделал распределение, следует инициализировать указатели на NULL. Обычно это делается в конструкторе объекта записи:

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

Наконец, необходимо переопределить функцию `DoBulkFieldExchange` участника. Для членов полевых данных позвоните в функции Bulk RFX; для любых параметров, членов данных, позвоните в функции RFX. Если вы открыли запись, передав выписку `Open`из S'L или хранив процедуру, то порядок, в котором вы делаете звонки Bulk RFX, должен соответствовать порядку столбцов в наборе записей; аналогичным образом, порядок rfX требует параметров, должны соответствовать порядку параметров в выписке или процедуре хранения.

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
> Вы должны `Close` вызвать функцию `CRecordset` участника, прежде чем ваш производный класс выйдет из сферы действия. Это гарантирует освобождение любой памяти, выделенной фреймворкой. Это хорошая практика программирования, `Close`чтобы всегда явно вызова, независимо от того, вы реализовали объем строки извлечения.

Для получения дополнительной информации об обмене рекордными полями (RFX) [см.](../../data/odbc/record-field-exchange-how-rfx-works.md) Для получения дополнительной информации об использовании параметров см. [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) и [Recordset: Parameterizing a Recordset (ODBC).](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

## <a name="see-also"></a>См. также раздел

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)
