---
title: Класс CDaoFieldExchange
ms.date: 11/04/2016
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
ms.openlocfilehash: ef88486d14ade1d5871d614069dc1c202d6ad159
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654224"
---
# <a name="cdaofieldexchange-class"></a>Класс CDaoFieldExchange

Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO.

## <a name="syntax"></a>Синтаксис

```
class CDaoFieldExchange
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Возвращает ненулевое значение, если текущая операция, соответствующие тип обновляемого поля.|
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|Указывает тип элемента данных набора записей — столбца или параметра, представленного до следующего вызова для всех последующих вызовов функций DFX `SetFieldType`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDaoFieldExchange::m_nOperation](#m_noperation)|DFX операция, выполняемая при вызове текущего набора записей `DoFieldExchange` функция-член.|
|[CDaoFieldExchange::m_prs](#m_prs)|Указатель на набор записей, на какие DFX выполняются операции.|

## <a name="remarks"></a>Примечания

`CDaoFieldExchange` не имеет базового класса.

Этот класс используется при создании процедуры данных exchange для пользовательских типов данных; в противном случае вы не будет использовать непосредственно этот класс. DFX обеспечивает обмен данными между элементами данных полей в [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта и соответствующие поля текущей записи в источнике данных. DFX управляет exchange в обоих направлениях, из источника данных и к источнику данных. См. в разделе [53 технические Примечание](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) сведения о написании пользовательские процедуры DFX.

> [!NOTE]
>  Классы баз данных DAO, отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классы MFC на основе ODBC. Классы на основе DAO можно получить доступ к данных, в том числе через драйверы ODBC, с помощью собственных компонент database engine. Они также поддерживают операции языка описания данных DDL, например добавление таблиц через классы вместо того, чтобы самостоятельно вызвать DAO.

> [!NOTE]
>  Обмен полями записей DAO (DFX) очень похоже на обмен полями записей (RFX) в классы баз данных MFC на основе ODBC ( `CDatabase`, `CRecordset`). Если вы понимаете RFX, вы найдете его DFX прост в использовании.

Объект `CDaoFieldExchange` предоставляет сведения о контексте требуется для DAO обмен полями вступили в силу записей. `CDaoFieldExchange` объекты поддерживают ряд операций, включая параметры привязки и поля элементов данных, а также установка различных флагов для полей текущей записи. DFX операции выполняются в членах данных набора записей класса типов, определенных **перечисления** **FieldType** в `CDaoFieldExchange`. Возможные **FieldType** значения:

- `CDaoFieldExchange::outputColumn` для поля элементов данных.

- `CDaoFieldExchange::param` для элементов данных параметров.

[IsValidOperation](#isvalidoperation) для написания собственных пользовательские процедуры DFX предоставляется функция-член. Вы воспользуетесь [SetFieldType](#setfieldtype) часто вашей [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) функции. Дополнительные сведения о глобальных функций DFX, см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md). Сведения о написании пользовательские процедуры DFX для собственных типов данных, см. в разделе [53 технические Примечание](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDaoFieldExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

##  <a name="isvalidoperation"></a>  CDaoFieldExchange::IsValidOperation

При написании собственной функции DFX, вызовите `IsValidOperation` в начале функции для определения ли текущая операция может выполняться на определенный тип члена данных ( `CDaoFieldExchange::outputColumn` или `CDaoFieldExchange::param`).

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если текущая операция не подходит для типа обновляемого поля.

### <a name="remarks"></a>Примечания

Некоторые операции, выполняемые с помощью механизма DFX применяются только к одной из возможных типов полей. Следуйте модели для существующих функций DFX.

Дополнительные сведения о создании пользовательские процедуры DFX, см. в разделе [53 технические Примечание](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

##  <a name="m_noperation"></a>  CDaoFieldExchange::m_nOperation

Определяет операцию, выполняемую на [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объект, связанный с объектом exchange поля.

### <a name="remarks"></a>Примечания

`CDaoFieldExchange` Предоставляет контекст для другой операции DFX для объекта recordset.

> [!NOTE]
>  Описано в разделе ниже операций MarkForAddNew и метод SetFieldNull PSEUDONULL значение является значением, используемую для обозначения поля Null. Механизм обмена полями записей DAO (DFX) использует это значение, чтобы определить, какие поля явным образом помеченные значение Null. PSEUDONULL не является обязательным для [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) и [COleCurrency](../../mfc/reference/colecurrency-class.md) поля.

Возможные значения `m_nOperation` являются:

|Операция|Описание|
|---------------|-----------------|
|`AddToParameterList`|Строит **параметры** предложения инструкции SQL.|
|`AddToSelectList`|Строит **ВЫБЕРИТЕ** предложения инструкции SQL.|
|`BindField`|Привязывает поле в базе данных на адрес памяти в приложении.|
|`BindParam`|Задает значения параметров для запроса набора записей.|
|`Fixup`|Задает допустимость значений Null для поля.|
|`AllocCache`|Выделяет кэш, используемый для проверки для полей «грязный» в наборе записей.|
|`StoreField`|Сохраняет текущую запись в кэш.|
|`LoadField`|Восстанавливает кэшированные данные переменных-членов в наборе записей.|
|`FreeCache`|Освобождает кэш, используемый для проверки для полей «грязный» в наборе записей.|
|`SetFieldNull`|Задает состояние поля Null и значение PSEUDONULL.|
|`MarkForAddNew`|Метки полей «грязный» Если не PSEUDONULL.|
|`MarkForEdit`|Помечает поля «грязный», если они не совпадают кэша.|
|`SetDirtyField`|Задает поле значения, помеченные как «грязный».|
|`DumpField`|Выводит содержимое поля (только для режима debug).|
|`MaxDFXOperation`|Используется для проверки ввода.|

##  <a name="m_prs"></a>  CDaoFieldExchange::m_prs

Содержит указатель на [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объект, связанный с `CDaoFieldExchange` объекта.

### <a name="remarks"></a>Примечания

##  <a name="setfieldtype"></a>  CDaoFieldExchange::SetFieldType

Вызовите `SetFieldType` в вашей `CDaoRecordset` класса `DoFieldExchange` переопределить.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Параметры

*nFieldType*<br/>
Значение **enum FieldType**, объявленные в `CDaoFieldExchange`, который может быть одно из следующих:

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>Примечания

Как правило ClassWizard создает этот вызов. Если написать собственную функцию и при использовании мастера для написания вашего `DoFieldExchange` функции, добавьте вызовы собственную функцию за пределами сопоставление полей. Если вы не используете мастер, не будет сопоставление полей. Вызов предшествует вызовов функций DFX, один для каждого элемента данных поля класса и определяет тип поля как `CDaoFieldExchange::outputColumn`.

Если вы параметризовать класса набора записей, следует добавлять вызовы DFX для всех элементов данных параметра (за пределами сопоставление полей) и предшествовать эти вызовы с вызовом `SetFieldType`. Передайте значение `CDaoFieldExchange::param`. (Вместо этого можно использовать [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) и значения его параметров.)

Как правило, каждой группы DFX вызовов функций, связанных с элементами данных полей или членов данных параметра должен предшествовать вызов `SetFieldType`. *NFieldType* параметр каждого `SetFieldType` вызова определяет тип элементов данных, представленный вызовы функции DFX, следуйте `SetFieldType` вызова.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)
