---
title: "Класс CDaoFieldExchange | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- field exchange
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- field exchange, record for DAO classes
- exchanging data between databases and recordsets
- DFX (DAO record field exchange), DAO Record Field Exchange
- RFX (record field exchange)
- CDaoFieldExchange class
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
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
ms.openlocfilehash: 31b7121f8e93f85ed73b5d095ac0995f3ddee721
ms.lasthandoff: 02/24/2017

---
# <a name="cdaofieldexchange-class"></a>Класс CDaoFieldExchange
Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoFieldExchange  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Возвращает ненулевое значение, если текущая операция, соответствующие тип обновляемого поля.|  
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|Указывает тип элемента данных набора записей, столбца или параметра, представленного все последующие вызовы функции DFX до следующего вызова для `SetFieldType`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDaoFieldExchange::m_nOperation](#m_noperation)|DFX операция, выполняемая текущего вызова к набору записей `DoFieldExchange` функции-члена.|  
|[CDaoFieldExchange::m_prs](#m_prs)|Указатель на набор записей, в которых DFX выполняются операции.|  
  
## <a name="remarks"></a>Примечания  
 `CDaoFieldExchange`не имеет базового класса.  
  
 Этот класс используется при создании процедуры обмена данными для пользовательских типов данных; в противном случае — не используется напрямую этого класса. DFX обеспечивает обмен данными между элементами данных полей вашего [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта и соответствующие поля текущей записи в источнике данных. DFX управляет обменом в обоих направлениях, из источника данных и в источнике данных. В разделе [53 Технические заметки](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) сведения о написании пользовательские процедуры DFX.  
  
> [!NOTE]
>  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Можно по-прежнему обращаться к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классов MFC на основе ODBC. Классы на основе DAO доступны данные, включая посредством драйверов ODBC, через свои собственные компонента database engine. Они также поддерживают операции языка определения данных (DDL), например добавление таблиц с помощью классов, вместо того, чтобы вызвать DAO.  
  
> [!NOTE]
>  Обмен полями записей DAO (DFX) очень похоже на обмен полями записей (RFX) в классы баз данных MFC на основе ODBC ( `CDatabase`, `CRecordset`). Если вы понимаете RFX, вы найдете его в использовании DFX.  
  
 Объект `CDaoFieldExchange` предоставляет сведения о контексте необходимые для DAO записать обмен полями вступили в силу. `CDaoFieldExchange`объекты поддерживают ряд операций, включая параметры привязки и элементами данных полей и параметр различные флаги полей текущей записи. DFX операций класс записей данные-члены типов, определенных `enum` **FieldType** в `CDaoFieldExchange`. Возможные **FieldType** значения:  
  
- **CDaoFieldExchange::outputColumn** для элементов данных полей.  
  
- **CDaoFieldExchange::param** для элементов данных параметров.  
  
 [IsValidOperation](#isvalidoperation) для написания пользовательских процедур DFX предоставлена функции-члена. Будет использоваться [SetFieldType](#setfieldtype) часто в вашей [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) функции. Дополнительные сведения о глобальных функций DFX см [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md). Сведения о создании пользовательские процедуры DFX для собственных типов данных см. в разделе [53 Технические заметки](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="isvalidoperation"></a>CDaoFieldExchange::IsValidOperation  
 При написании собственной функции DFX вызвать `IsValidOperation` в начале функции, чтобы определить, можно ли выполнить текущую операцию на определенный тип члена данных ( **CDaoFieldExchange::outputColumn** или **CDaoFieldExchange::param**).  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если текущая операция подходит для типа обновляемое поле.  
  
### <a name="remarks"></a>Примечания  
 Некоторые операции, выполняемые с помощью механизма DFX применяются только к одной из возможных типов полей. Следуйте модели для существующих функций DFX.  
  
 Дополнительные сведения о создании пользовательские процедуры DFX разделе [53 Технические заметки](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
##  <a name="m_noperation"></a>CDaoFieldExchange::m_nOperation  
 Определяет операцию, выполняемую на [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) связанный с объектом exchange поля.  
  
### <a name="remarks"></a>Примечания  
 `CDaoFieldExchange` Предоставляет контекст для нескольких различных операций DFX для набора записей.  
  
> [!NOTE]
>  **PSEUDONULL** значения, описанные в разделе MarkForAddNew метод SetFieldNull операции и ниже значение используется, чтобы пометить поля Null. Механизм обмена полями записей DAO (DFX) использует это значение, чтобы определить, какие поля явно помечены Null. **PSEUDONULL** не является обязательным для [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) и [COleCurrency](../../mfc/reference/colecurrency-class.md) полей.  
  
 Возможные значения **m_nOperation** являются:  
  
|Операция|Описание|  
|---------------|-----------------|  
|**AddToParameterList**|Строит **параметры** предложения инструкции SQL.|  
|**AddToSelectList**|Строит **ВЫБЕРИТЕ** предложения инструкции SQL.|  
|**BindField**|Привязывает поле в базе данных в ячейку памяти в приложении.|  
|**BindParam**|Задает значения параметров для запроса набора записей.|  
|**Исправление**|Задает состояние Null для поля.|  
|**AllocCache**|Выделяет кэш, используемый для проверки «грязных» поля в наборе записей.|  
|**StoreField**|Сохраняет текущую запись в кэш.|  
|**LoadField**|Восстанавливает переменные-члены кэшированных данных в наборе записей.|  
|**FreeCache**|Освобождает кэш, используемый для проверки «грязных» поля в наборе записей.|  
|`SetFieldNull`|Задает состояние поля Null и значение для **PSEUDONULL**.|  
|**MarkForAddNew**|Помечает поля «грязных», если не **PSEUDONULL**.|  
|**MarkForEdit**|Помечает поля «грязных», если они не совпадают, кэш.|  
|**SetDirtyField**|Присваивает полю значения, помеченные как «грязный».|  
|**DumpField**|Выводит содержимое поля (Отладка).|  
|**MaxDFXOperation**|Используется для проверки ввода.|  
  
##  <a name="m_prs"></a>CDaoFieldExchange::m_prs  
 Содержит указатель на [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, связанного с `CDaoFieldExchange` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfieldtype"></a>CDaoFieldExchange::SetFieldType  
 Вызов `SetFieldType` в ваш `CDaoRecordset` класса `DoFieldExchange` переопределить.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Параметры  
 `nFieldType`  
 Значение **enum FieldType**, объявленные в `CDaoFieldExchange`, который может быть одним из следующих:  
  
- **CDaoFieldExchange::outputColumn**  
  
- **CDaoFieldExchange::param**  
  
### <a name="remarks"></a>Примечания  
 Как правило ClassWizard создает этот вызов. Если написать собственную функцию и записи с помощью мастера вашей `DoFieldExchange` добавьте вызовы функции за пределами сопоставления полей. Если мастер не используется, не будет сопоставления полей. Вызов предшествует вызовы функций DFX, один для каждого члена данных поля класса и определяет тип поля как **CDaoFieldExchange::outputColumn**.  
  
 Параметризация класса набора записей, необходимо добавить вызовы DFX для всех элементов данных параметров (за пределами сопоставления полей) и перед вызовом этих вызовов `SetFieldType`. Передайте значение **CDaoFieldExchange::param**. (Вместо этого можно использовать [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) и значения его параметров.)  
  
 Как правило, каждой группы DFX вызовы функций, связанных с элементами данных полей или членов данных параметра должен предшествовать вызов `SetFieldType`. `nFieldType` Параметр каждого `SetFieldType` вызова определяет тип элементов данных, представленных DFX вызовы функции, выполните `SetFieldType` вызова.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset-класс](../../mfc/reference/cdaorecordset-class.md)

