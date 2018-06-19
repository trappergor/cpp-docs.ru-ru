---
title: 'Набор записей: Пакетная выборка строк (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8ef8803459edeba98e472a0e7fd07e7f5daf2c4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097898"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Набор записей: пакетная выборка строк (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Класс `CRecordset` обеспечивает поддержку выборка строк, что означает, что несколько записей можно извлечь за один раз во время одной выборки, а не получение одной записи за раз из источника данных. Можно реализовать выборка строк только в производном `CRecordset` класса. Процесс переноса данных из источника данных в объект набора записей называется блочный обмен полей записей (Bulk RFX). Обратите внимание, что если вы не используете массовая выборка строк `CRecordset`-производного класса, данные передаются посредством обмена полями записей (RFX). Дополнительные сведения см. в разделе [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
 Содержание раздела:  
  
-   [Как CRecordset поддерживает выборка строк](#_core_how_crecordset_supports_bulk_row_fetching).  
  
-   [Некоторые специальные рекомендации при использовании пакетная выборка строк](#_core_special_considerations).  
  
-   [Как реализовать блочный обмен полей записей](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> Как CRecordset поддерживает выборку строк  
 Перед открытием объекта набора записей, можно определить размер набора строк с `SetRowsetSize` функции-члена. Размер набора строк определяет, сколько записей должно быть извлечено за одну операцию выборки. При реализации массовой выборки строк, размер набора строк по умолчанию — 25. Если выборка строк не реализована, размер набора строк остается равным 1.  
  
 После установки размера набора строк вызовите [откройте](../../mfc/reference/crecordset-class.md#open) функции-члена. Необходимо указать `CRecordset::useMultiRowFetch` параметр **dwOptions** параметра выборка строк. Кроме того, можно установить **CRecordset::userAllocMultiRowBuffers** параметр. Механизм обмена полями записей массового использует массивы для хранения нескольких строк данных, полученных во время выборки. Буферы хранения могут быть выделены автоматически платформой, или они могут быть добавлены вручную. Указание **CRecordset::userAllocMultiRowBuffers** параметр означает, что будет выполнить выделение.  
  
 В следующей таблице перечислены функции-члены, предоставляемые `CRecordset` для поддержки выборка строк.  
  
|Функция-член|Описание|  
|---------------------|-----------------|  
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|Виртуальная функция, которая обрабатывает ошибки, возникающие во время выборки.|  
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Реализует блочный обмен полей записей. Вызывается автоматически для передачи нескольких строк данных из источника данных в объект набора записей.|  
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Извлекает текущее значение размера набора строк.|  
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Сообщает, сколько строк было в действительности извлечено после операции выборки. В большинстве случаев это размер набора строк, если не неполного набора строк, которые были выбраны.|  
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Возвращает состояние выборки для конкретной строки в наборе строк.|  
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Обновляет данные и статус конкретной строки в наборе строк.|  
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|Перемещает курсор к конкретной строки в наборе строк.|  
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Виртуальная функция, которая изменяет параметр размера набора строк с указанным значением.|  
  
##  <a name="_core_special_considerations"></a> Специальные условия  
 Несмотря на то, что выборка строк дает выигрыш в производительности, некоторые функции работают по-разному. Прежде чем выборка строк, учтите следующее:  
  
-   Платформа автоматически вызывает `DoBulkFieldExchange` функции-члена для передачи данных из источника данных в объект набора записей. Однако данные не передаются из набора записей в источнике данных. Вызов `AddNew`, **изменить**, **удаление**, или **обновление** результаты функции члена в утверждение, вызвавшее сбой. Несмотря на то что `CRecordset` в настоящее время не предоставляет механизм для обновления пакетов строк данных, можно написать свои собственные функции с помощью функции API-интерфейса ODBC **SQLSetPos**. Дополнительные сведения о **SQLSetPos**, в разделе *справочнике программиста ODBC SDK* в документации MSDN.  
  
-   Функции-члены `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty`, и `SetFieldNull` не может использоваться с наборами записей, выборка строк. Тем не менее, можно вызвать `GetRowStatus` вместо `IsDeleted`, и `GetODBCFieldInfo` вместо `IsFieldNullable`.  
  
-   **Переместить** операции перемещают набор записей по набору строк. Например предположим, что открыть набор записей, 100 записей с начальным размером набора строк из 10. **Откройте** производит выборку строк от 1 до 10, при этом текущая запись помещается на строку 1. Вызов `MoveNext` извлекает следующего набора строк, а не следующей строки. Этот набор строк состоит из строки с 11 по 20, при этом текущая запись помещается на строку 11. Обратите внимание, что `MoveNext` и **Move (1)** не эквивалентны, при реализации массовой выборки строк. **Move (1)** извлекает набор строк, который начинается с первой строки с текущей записью. В этом примере вызов **Move (1)** после вызова **откройте** извлекает набор строк, состоящий из строк со 2 по 11, при этом текущая запись позиционируется на строку 2. Дополнительные сведения см. в разделе [переместить](../../mfc/reference/crecordset-class.md#move) функции-члена.  
  
-   В отличие от обмен полями записей мастера не поддерживают блочный обмен полей записей. Это означает, что необходимо вручную объявить члены-поля данных и вручную переопределить `DoBulkFieldExchange` используя вызовы функций Bulk RFX. Дополнительные сведения см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md) в *Справочник по библиотеке классов*.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> Как реализовать блочный обмен полей записей  
 Блочный обмен полей записей передает набор строк данных из источника данных объекта набора записей. Функции Bulk RFX используют для хранения этих данных, а также для хранения длины каждого элемента данных в наборе строк. В определении класса необходимо определить члены-поля данных как указатели для доступа к массивам данных. Кроме того необходимо определить набор указателей для доступа к массивам длин. Членов данных параметров не должен быть объявлен как указатели; объявление членов данных параметров при использовании блочный обмен полей записей является таким же, как их объявления при использовании обмен полями записей. Ниже приведен простой пример:  
  
```  
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
  
 Можно выделить буферы хранения вручную или было произведено средой выполнения распределения. Чтобы выделить буферы самостоятельно, необходимо указать **CRecordset::userAllocMultiRowBuffers** параметр **dwOptions** параметр в **откройте** функции-члена. Не забудьте установить размеры массивов по крайней мере равно размеру набора строк. Если вы хотите иметь средой выполнения распределения, инициализируйте указатели для **значение NULL.** Обычно это делается в конструкторе объекта набора записей:  
  
```  
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
  
 Наконец, необходимо переопределить `DoBulkFieldExchange` функции-члена. Для поля элементов данных вызова функций Bulk RFX; для элементов данных параметров вызовите функции RFX. Если набор записей открыт, передавая инструкцию SQL или хранимую процедуру для **откройте**, порядок, в котором производятся вызовы функций Bulk RFX должен совпадать с порядком столбцов в наборе записей, аналогичным образом, вызовы порядок RFX параметры должны совпадать с порядком параметров в инструкции SQL или хранимой процедуры.  
  
```  
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
>  Необходимо вызвать **закрыть** функции-члена производного перед `CRecordset` класс выходит за пределы области. Это гарантирует, что память, выделенная платформой освобождаются. Это в общем случае рекомендуется всегда явно вызвать **закрыть**, независимо от того, реализуется ли пакетная выборка строк.  
  
 Дополнительные сведения о обмен полями записей (RFX) см. в разделе [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Дополнительные сведения об использовании параметров см. в разделе [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) и [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)   
 [CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

