---
title: "Класс CDaoFieldExchange | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4a62d3f9631d4e2807bf12e1eda3bd4b4f5112
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdaofieldexchange-class"></a>Класс CDaoFieldExchange
Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDaoFieldExchange  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Возвращает ненулевое значение, если текущая операция подходит для типа обновляемого поля.|  
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|Указывает тип элемента данных набора записей — столбца или параметра, представленного все последующие вызовы функций DFX до следующего вызова для `SetFieldType`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDaoFieldExchange::m_nOperation](#m_noperation)|DFX операцию, выполняемую при вызове текущего набора записей `DoFieldExchange` функции-члена.|  
|[CDaoFieldExchange::m_prs](#m_prs)|Указатель на набор записей, на какие DFX выполняются операции.|  
  
## <a name="remarks"></a>Примечания  
 `CDaoFieldExchange`не имеет базового класса.  
  
 Этот класс используется при создании процедуры обмена данными для пользовательских типов данных; в противном случае не используется напрямую этого класса. DFX обеспечивает обмен данными между элементами данных полей в [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта и соответствующие поля текущей записи в источнике данных. DFX управляет exchange в обоих направлениях из источника данных, а также к источнику данных. В разделе [Технические заметки 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) сведения о написании пользовательские процедуры DFX.  
  
> [!NOTE]
>  Классы баз данных DAO отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классы MFC на основе ODBC. Классы на основе DAO доступны данные, включая через драйверы ODBC, через свои собственные компонента database engine. Они также поддерживают операции языка определения данных (DDL), например добавление таблиц с помощью классов, вместо того, чтобы самостоятельно вызвать DAO.  
  
> [!NOTE]
>  Обмен полями записей DAO (DFX) очень похож на обмен полями записей (RFX) в классы баз данных MFC на основе ODBC ( `CDatabase`, `CRecordset`). Если понимаете RFX, вы обнаружите его удобные DFX.  
  
 Объект `CDaoFieldExchange` предоставляет сведения о контексте требуется для DAO обмен полями вступили в силу записей. `CDaoFieldExchange`объекты поддерживают ряд операций, включая параметры привязки и полей данных и установки различных флагов для полей текущей записи. DFX операций, для членов класса набора записей данных типов, определенных `enum` **FieldType** в `CDaoFieldExchange`. Возможные **FieldType** значения:  
  
- **CDaoFieldExchange::outputColumn** для элементов данных полей.  
  
- **CDaoFieldExchange::param** для элементов данных параметров.  
  
 [IsValidOperation](#isvalidoperation) для написания собственные пользовательские процедуры DFX предоставлена функции-члена. Вы воспользуетесь [SetFieldType](#setfieldtype) часто в вашей [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) функции. Дополнительные сведения о глобальных функций DFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md). Сведения о написании пользовательские процедуры DFX для собственных типов данных см. в разделе [Технические заметки 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
##  <a name="isvalidoperation"></a>CDaoFieldExchange::IsValidOperation  
 При написании собственной функции DFX, вызовите `IsValidOperation` в начале функцию таким образом, чтобы определить, можно ли выполнить текущую операцию с типом члена определенного поля данных ( **CDaoFieldExchange::outputColumn** или **CDaoFieldExchange::param**).  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если текущая операция не подходит для обновляемого поля типа.  
  
### <a name="remarks"></a>Примечания  
 Некоторые операции, выполняемые с помощью механизма DFX применимы только к одной из возможных типов полей. Следуйте модели для существующих функций DFX.  
  
 Дополнительные сведения о создании пользовательские процедуры DFX. в разделе [Технические заметки 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
##  <a name="m_noperation"></a>CDaoFieldExchange::m_nOperation  
 Определяет операцию, выполняемых на [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объект, связанный с объектом exchange поля.  
  
### <a name="remarks"></a>Примечания  
 `CDaoFieldExchange` Предоставляет контекст для нескольких различных операций DFX для набора записей.  
  
> [!NOTE]
>  **PSEUDONULL** значения, описанные в разделе MarkForAddNew метод SetFieldNull операции и ниже значение используется для пометки поля Null. Механизм обмена полями записей DAO (DFX) использует это значение, чтобы определить, какие поля явно помечены в Null. **PSEUDONULL** не является обязательным для [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) и [COleCurrency](../../mfc/reference/colecurrency-class.md) поля.  
  
 Возможные значения **m_nOperation** являются:  
  
|Операция|Описание:|  
|---------------|-----------------|  
|**AddToParameterList**|Выполняет построение **параметры** предложения инструкции SQL.|  
|**AddToSelectList**|Выполняет построение **ВЫБЕРИТЕ** предложения инструкции SQL.|  
|**BindField**|Привязывает поле в базе данных в ячейку памяти в приложении.|  
|**BindParam**|Задает значения параметров для запроса набора записей.|  
|**Адресная привязка**|Задает допустимость значений Null для поля.|  
|**AllocCache**|Выделяет кэш, используемый для проверки «грязных» поля в наборе записей.|  
|**StoreField**|Сохраняет текущую запись в кэш.|  
|**LoadField**|Восстанавливает переменных-членов кэшированные данные в наборе записей.|  
|**FreeCache**|Освобождает кэш, используемый для проверки «грязных» поля в наборе записей.|  
|`SetFieldNull`|Задает состояние поля Null и значение **PSEUDONULL**.|  
|**MarkForAddNew**|Помечает поля «грязных», если не **PSEUDONULL**.|  
|**MarkForEdit**|Помечает поля «грязных», если они не соответствуют кэша.|  
|**SetDirtyField**|Присваивает полю значения, помеченные как «грязных».|  
|**DumpField**|Выводит содержимое поля (Отладка).|  
|**MaxDFXOperation**|Используется для проверки ввода.|  
  
##  <a name="m_prs"></a>CDaoFieldExchange::m_prs  
 Содержит указатель на [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта, связанного с `CDaoFieldExchange` объекта.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfieldtype"></a>CDaoFieldExchange::SetFieldType  
 Вызовите `SetFieldType` в ваш `CDaoRecordset` класса `DoFieldExchange` переопределения.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Параметры  
 `nFieldType`  
 Значение **enum FieldType**, объявленные в `CDaoFieldExchange`, который может быть одно из следующих:  
  
- **CDaoFieldExchange::outputColumn**  
  
- **CDaoFieldExchange::param**  
  
### <a name="remarks"></a>Примечания  
 Как правило мастер ClassWizard создает этот вызов. Если написать собственную функцию и записи с помощью мастера вашей `DoFieldExchange` функционировать, добавьте вызовы функции за пределами сопоставления полей. Если вы не используете мастер, не будет сопоставление полей. Вызов предшествует вызовы функций DFX, один для каждого элемента данных поля класса и определяет тип поля как **CDaoFieldExchange::outputColumn**.  
  
 Если можно параметризовать класса набора записей, следует добавлять вызовы DFX для всех членов данных параметра (за пределами сопоставления полей) и перед вызовом этих вызовов `SetFieldType`. Передайте значение **CDaoFieldExchange::param**. (Вместо этого можно использовать [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) и значения его параметров.)  
  
 Как правило, каждой группы DFX вызовы функций, связанных с элементами данных полей или членов данных параметра должен предшествовать вызов `SetFieldType`. `nFieldType` Параметр каждого `SetFieldType` вызова определяет тип данных элементы, представленные на вызовы функции DFX, следующие за `SetFieldType` вызова.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)
