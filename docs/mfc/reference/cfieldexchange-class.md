---
title: Класс разделе | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs:
- C++
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d20a89e48475a0226d76ac719459b1b99cc4e355
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cfieldexchange-class"></a>Класс разделе
Поддерживает процедуры обмена полями записей (RFX) и блочного обмена полями записей (Bulk RFX), используемые классами баз данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|Возвращает ненулевое значение, если текущая операция подходит для типа обновляемого поля.|  
|[CFieldExchange::SetFieldType](#setfieldtype)|Указывает тип элемента данных набора записей — столбца или параметра, представленного все следующие вызовы функций RFX до следующего вызова для `SetFieldType`.|  
  
## <a name="remarks"></a>Примечания  
 `CFieldExchange`не имеет базового класса.  
  
 Этот класс используется при создании процедуры обмена данными для пользовательских типов данных или при реализации массовой выборки строк; в противном случае не используется напрямую этого класса. RFX и Bulk RFX обеспечивает обмен данными между элементами данных полей объекта набора записей и соответствующие поля текущей записи в источнике данных.  
  
> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO), а не классы Open Database Connectivity (ODBC), используйте класс [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) вместо него. Дополнительные сведения см. в статье [программирования Обзор: база данных](../../data/data-access-programming-mfc-atl.md).  
  
 Объект `CFieldExchange` предоставляет сведения о контексте требуется для обмен полями записей или блочный обмен полей записей, чтобы воспользоваться поместите. `CFieldExchange`объекты поддерживают ряд операций, включая параметры привязки и полей данных и установки различных флагов для полей текущей записи. RFX и Bulk RFX операций, для членов класса набора записей данных типов, определенных `enum` **FieldType** в `CFieldExchange`. Возможные **FieldType** значения:  
  
- **CFieldExchange::outputColumn** для элементов данных полей.  
  
- **CFieldExchange::inputParam** или **CFieldExchange::param** для членов данных входного параметра.  
  
- **CFieldExchange::outputParam** для членов данных выходного параметра.  
  
- **CFieldExchange::inoutParam** для членов данных входным или выходным параметром.  
  
 Большинство членов класса члена функции и данные предоставляются для написания пользовательских процедур RFX. Вы воспользуетесь `SetFieldType` часто. Дополнительные сведения см. в статьях [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [записей (ODBC)](../../data/odbc/recordset-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения о глобальных функций RFX и Bulk RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md) раздела макросов MFC и глобальные объекты из этой ссылки.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CFieldExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
##  <a name="isfieldtype"></a>CFieldExchange::IsFieldType  
 При написании собственной функции RFX, вызовите `IsFieldType` в начале функцию таким образом, чтобы определить, можно ли выполнить текущую операцию для определенного поля или параметра член типа данных ( **CFieldExchange::outputColumn**, **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, или **CFieldExchange::inoutParam** ).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>Параметры  
 *pnField*  
 В этом параметре возвращается порядковый номер элемента данных поля или параметра. Это число соответствует член данных заказа в [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если текущая операция может быть выполнена в текущем типе, поля или параметра.  
  
### <a name="remarks"></a>Примечания  
 Следуйте модели для существующих функций RFX.  
  
##  <a name="setfieldtype"></a>CFieldExchange::SetFieldType  
 Необходим вызов `SetFieldType` в классе записей [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) переопределения.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Параметры  
 `nFieldType`  
 Значение **enum FieldType**, объявленные в `CFieldExchange`, который может принимать одно из следующих действий:  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>Примечания  
 Члены данных полей, необходимо вызвать `SetFieldType` с параметром **CFieldExchange::outputColumn**, а затем вызовы функций RFX и Bulk RFX. Если вы не реализована массовая выборка строк, то ClassWizard помещает это `SetFieldType` вызова для вас в разделе полей карты `DoFieldExchange`.  
  
 Если вы параметризовать класса набора записей, необходимо вызвать `SetFieldType` , за пределами любого раздела сопоставления полей, а затем вызовы функций RFX для всех членов данных параметра. Каждый тип члена данных параметра должен иметь свой собственный `SetFieldType` вызова. Следующая таблица различает разные значения, можно передать в `SetFieldType` для представления элементов данных параметров вашего класса:  
  
|Значение параметра SetFieldType|Тип элемента данных, параметр|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|Входной параметр. Значение, которое было передано в наборе записей запроса или хранимой процедуры.|  
|**CFieldExchange::param**|То же, что **CFieldExchange::inputParam**.|  
|**CFieldExchange::outputParam**|Выходной параметр. Возвращаемое значение хранимой процедуры набора записей.|  
|**CFieldExchange::inoutParam**|Входным или выходным параметром. Значение, которое передается в и возвращаемым из хранимой процедуры набора записей.|  
  
 Как правило, каждой группы функции RFX, связанные с элементами данных полей или членов данных параметра должен предшествовать вызов `SetFieldType`. `nFieldType` Параметр каждого `SetFieldType` вызова определяет тип элементов данных, представленный последующих вызовов функций RFX `SetFieldType` вызова.  
  
 Дополнительные сведения об обработке выходные данные и параметры ввода вывода см. в разделе `CRecordset` функции-члена [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). Дополнительные сведения о функции RFX и Bulk RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md). Дополнительные сведения о массовой выборке строк см. в статье [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Пример  
 В этом примере показано несколько вызовов функций RFX с сопутствующими вызовы `SetFieldType`. Обратите внимание, что `SetFieldType` вызывается через `pFX` указатель `CFieldExchange` объекта.  
  
 [!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)
