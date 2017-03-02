---
title: "Класс разделе | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFieldExchange
dev_langs:
- C++
helpviewer_keywords:
- enum FieldType, CFieldExchange
- RFX (record field exchange) [C++]
- RFX (record field exchange) [C++], classes for
- CFieldExchange class
- FieldType enumeration
- data types [C++], custom
- enum FieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 948f13dc54fcd83941bab8e63b2ab2704d84cb87
ms.lasthandoff: 02/24/2017

---
# <a name="cfieldexchange-class"></a>Класс разделе
Поддерживает процедуры обмена полями записей (RFX) и блочного обмена полями записей (Bulk RFX), используемые классами баз данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|Возвращает ненулевое значение, если текущая операция, соответствующие тип обновляемого поля.|  
|[CFieldExchange::SetFieldType](#setfieldtype)|Указывает тип элемента данных набора записей, столбца или параметра, представленного все следующие вызовы функций RFX до следующего вызова для `SetFieldType`.|  
  
## <a name="remarks"></a>Примечания  
 `CFieldExchange`не имеет базового класса.  
  
 Этот класс используется при создании процедуры обмена данными для пользовательских типов данных или если вы реализуете выборка строк; в противном случае — не используется напрямую этого класса. RFX и Bulk RFX обмен данными между элементами данных полей объекта набора записей и соответствующие поля текущей записи в источнике данных.  
  
> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO), а не классы Open Database Connectivity (ODBC), используйте класс [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) вместо. Дополнительные сведения см. в статье [программирования Обзор: база данных](../../data/data-access-programming-mfc-atl.md).  
  
 Объект `CFieldExchange` предоставляет сведения о контексте необходимые для обмена полями записей или блочный обмен полей записей, чтобы воспользоваться поместите. `CFieldExchange`объекты поддерживают ряд операций, включая параметры привязки и элементами данных полей и параметр различные флаги полей текущей записи. RFX и Bulk RFX операций класс записей данные-члены типов, определенных `enum` **FieldType** в `CFieldExchange`. Возможные **FieldType** значения:  
  
- **CFieldExchange::outputColumn** для элементов данных полей.  
  
- **CFieldExchange::inputParam** или **CFieldExchange::param** для членов данных входного параметра.  
  
- **CFieldExchange::outputParam** для членов данных выходного параметра.  
  
- **CFieldExchange::inoutParam** для элементов данных параметров ввода вывода.  
  
 Большинство членов класса члена функции и данные предоставляются для написания пользовательских процедур RFX. Будет использоваться `SetFieldType` часто. Дополнительные сведения см. в статьях [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [записей (ODBC)](../../data/odbc/recordset-odbc.md). Дополнительные сведения о групповой выборке строк см. в статье [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения о глобальных функций RFX и Bulk RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md) в разделе макросов MFC и глобальные объекты этой ссылки.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CFieldExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
##  <a name="a-nameisfieldtypea--cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a>CFieldExchange::IsFieldType  
 При написании собственной функции RFX вызвать `IsFieldType` в начале функции, чтобы определить, можно выполнить текущую операцию для определенного поля или параметра член типа данных ( **CFieldExchange::outputColumn**, **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, или **CFieldExchange::inoutParam**).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>Параметры  
 *pnField*  
 В этом параметре возвращается порядковый номер элемента поля или параметра. Это число соответствует порядок членов данных в [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если текущая операция может быть выполнена для текущего типа поля или параметра.  
  
### <a name="remarks"></a>Примечания  
 Следуйте модели для существующих функций RFX.  
  
##  <a name="a-namesetfieldtypea--cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a>CFieldExchange::SetFieldType  
 Необходим вызов `SetFieldType` в классе записей [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) переопределить.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Параметры  
 `nFieldType`  
 Значение **enum FieldType**, объявленные в `CFieldExchange`, который может принимать одно из следующих:  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>Примечания  
 Члены данных полей, необходимо вызвать `SetFieldType` с параметром **CFieldExchange::outputColumn**, следуют вызовы функций RFX и Bulk RFX. Если выборка строк не реализована, то ClassWizard помещает это `SetFieldType` вызова для вас в разделе сопоставления поля `DoFieldExchange`.  
  
 Параметризация класса набора записей, необходимо вызвать `SetFieldType` снова, за пределами любого раздела сопоставления полей, за которым следует вызовы функций RFX для всех элементов данных параметров. Каждый тип члена данных параметра должен иметь свой собственный `SetFieldType` вызова. Следующая таблица отличает разные значения, можно передать `SetFieldType` для представления элементов данных параметров класса:  
  
|Значение параметра SetFieldType|Тип элемента данных, параметр|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|Входной параметр. Значение, передаваемое в наборе записей запроса или хранимой процедуры.|  
|**CFieldExchange::param**|То же, что **CFieldExchange::inputParam**.|  
|**CFieldExchange::outputParam**|Выходной параметр. Возвращаемое значение хранимой процедуры набора записей.|  
|**CFieldExchange::inoutParam**|Параметр ввода вывода. Значение, которое передается в и возвращаемым из хранимой процедуры набора записей.|  
  
 Как правило, каждой группы функции RFX, связанные с элементами данных полей или членов данных параметра должен предшествовать вызов `SetFieldType`. `nFieldType` Параметр каждого `SetFieldType` вызова определяет тип элементов данных, представленных последующих вызовов функций RFX `SetFieldType` вызова.  
  
 Дополнительные сведения об обработке выходные данные и входные и выходные параметры в разделе `CRecordset` функции-члена [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). Дополнительные сведения о функциях RFX и Bulk RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md). Дополнительные сведения о групповой выборке строк см. в статье [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
 В этом примере показано несколько вызовов функции RFX оно вызовы `SetFieldType`. Обратите внимание, что `SetFieldType` вызывается через `pFX` указатель на `CFieldExchange` объект.  
  
 [!code-cpp[NVC_MFCDatabase&#33;](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)

