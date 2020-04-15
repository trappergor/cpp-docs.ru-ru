---
title: Класс CDaoFieldExchange
ms.date: 09/17/2019
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
ms.openlocfilehash: e1ce6e13b9c6045881cc0bb4114a6e11d58365c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368994"
---
# <a name="cdaofieldexchange-class"></a>Класс CDaoFieldExchange

Поддерживает процедуры обмена полями записей (DAO DFX), используемые классами баз данных DAO.

DAO поддерживается через Office 2013. DAO 3.6 является окончательной версией, и он считается устаревшим.

## <a name="syntax"></a>Синтаксис

```
class CDaoFieldExchange
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Возвращает ненулевой, если текущая операция подходит для типа обновления поля.|
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|Обрасывает тип члена данных записей - столбец или параметр - представленный всеми `SetFieldType`последующими вызовами к функциям DFX до следующего вызова.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDaoFieldExchange::m_nOperation](#m_noperation)|Операция DFX выполняется текущим вызовом к `DoFieldExchange` функции участника записи.|
|[CDaoFieldExchange:::m_prs](#m_prs)|Указатель на рекорд, на котором выполняются операции DFX.|

## <a name="remarks"></a>Remarks

`CDaoFieldExchange`не имеет базового класса.

Используйте этот класс, если вы пишете процедуры обмена данными для типов пользовательских данных; в противном случае вы не будете непосредственно использовать этот класс. DFX обменивается данными между полевыми данными объекта [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) и соответствующими полями текущей записи источника данных. DFX управляет обменом в обоих направлениях, от источника данных и источника данных. См [Технический примечание 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) для получения информации о написании пользовательских процедур DFX.

> [!NOTE]
> Классы баз данных DAO отличаются от классов баз данных MFC на основе open Database Connectivity (ODBC). Все названия классов баз данных DAO имеют префикс "CDao". Вы все еще можете получить доступ к источникам данных ODBC с классами DAO. В целом, классы МФЦ на основе DAO более способны, чем классы MFC на основе ODBC. Классы на базе ДАО могут получать доступ к данным, в том числе через драйверы ODBC, через свой собственный движок баз данных. Они также поддерживают операции language Definition Language data (DDL), такие как добавление таблиц через классы вместо того, чтобы называть DAO самостоятельно.

> [!NOTE]
> DAO обмена поля записи (DFX) очень похож на запись обмена поля (RFX) `CDatabase` `CRecordset`в ODBC основе MFC баз данных классов (, ). Если вы понимаете RFX, вы найдете его простым в использовании DFX.

Объект `CDaoFieldExchange` предоставляет контекстную информацию, необходимую для обмена полями записей DAO. `CDaoFieldExchange`объекты поддерживают ряд операций, включая параметры связывания и составы полевых данных и установку различных флагов на полях текущей записи. Операции DFX выполняются на данных регистраторов типов типов, определенных **enum** **FieldType** в `CDaoFieldExchange`. Возможные значения **FieldType:**

- `CDaoFieldExchange::outputColumn`для членов полевых данных.

- `CDaoFieldExchange::param`для членов параметров данных.

Функция участника [IsValidOperation](#isvalidoperation) предназначена для написания собственных пользовательских процедур DFX. Вы будете часто использовать [SetFieldType](#setfieldtype) в своих функциях [CDaoRecordset::DoFieldExchange.](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) Подробную информацию о глобальных функциях DFX можно узнать на примере [функций обмена на местах Record.](../../mfc/reference/record-field-exchange-functions.md) Для получения информации о написании пользовательских процедур DFX для собственных типов данных [см.](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CDaoFieldExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="cdaofieldexchangeisvalidoperation"></a><a name="isvalidoperation"></a>CDaoFieldExchange::IsValidOperation

Если вы пишете свою собственную функцию DFX, позвоните `IsValidOperation` в начале функции, чтобы определить, может ли текущая операция быть выполнена на определенном типе данных поля (a `CDaoFieldExchange::outputColumn` или a). `CDaoFieldExchange::param`

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если текущая операция подходит для типа обновления поля.

### <a name="remarks"></a>Remarks

Некоторые операции, выполняемые механизмом DFX, применяются только к одному из возможных типов полей. Следуйте модели существующих функций DFX.

Для получения дополнительной информации о написании пользовательских процедур DFX [см.](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)

## <a name="cdaofieldexchangem_noperation"></a><a name="m_noperation"></a>CDaoFieldExchange::m_nOperation

Определяет операцию, выполняемую на объекте [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) связанном с объектом обмена поля.

### <a name="remarks"></a>Remarks

Объект `CDaoFieldExchange` предоставляет контекст для ряда различных операций DFX на рекорде.

> [!NOTE]
> Значение PSEUDONULL, описанное в операциях MarkForAddNew и SetFieldNull ниже, является значением, используемым для обозначения полей Null. Механизм обмена полями записи DAO (DFX) использует это значение для определения того, какие поля были явно помечены Null. PSEUDONULL не требуется для [полей COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) и [COleCurrency.](../../mfc/reference/colecurrency-class.md)

`m_nOperation` Возможные значения:

|Операция|Описание|
|---------------|-----------------|
|`AddToParameterList`|Создает пункт **PARAMETERS** заявления S'L.|
|`AddToSelectList`|Создает пункт **SELECT** выписки s'L.|
|`BindField`|Связывает поле в базе данных с местом памяти в приложении.|
|`BindParam`|Устанавливает значения параметров для запроса записи.|
|`Fixup`|Устанавливает статус Null для поля.|
|`AllocCache`|Выделяет кэш, используемый для проверки "грязных" полей в наборе записей.|
|`StoreField`|Сохраняет текущую запись в кэше.|
|`LoadField`|Восстанавливает переменные кэшированных данных в наборе записей.|
|`FreeCache`|Освобождает кэш, используемый для проверки "грязных" полей в наборе записей.|
|`SetFieldNull`|Устанавливает статус поля на null и значение для PSEUDONULL.|
|`MarkForAddNew`|Отметки поля "грязные", если не PSEUDONULL.|
|`MarkForEdit`|Отметки полей "грязные", если они не совпадают с кэшем.|
|`SetDirtyField`|Устанавливает значения полей, помеченные как "грязные".|
|`DumpField`|Сбрасывает содержимое поля (только отлажается).|
|`MaxDFXOperation`|Используется для проверки ввода.|

## <a name="cdaofieldexchangem_prs"></a><a name="m_prs"></a>CDaoFieldExchange:::m_prs

Содержит указатель на объект [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) связанный с объектом. `CDaoFieldExchange`

### <a name="remarks"></a>Remarks

## <a name="cdaofieldexchangesetfieldtype"></a><a name="setfieldtype"></a>CDaoFieldExchange::SetFieldType

Звоните `SetFieldType` `CDaoRecordset` в `DoFieldExchange` переопределение вашего класса.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Параметры

*nFieldType*<br/>
Значение **enum FieldType**, заявлено в `CDaoFieldExchange`, который может быть любой из следующих:

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>Remarks

Как правило, ClassWizard пишет этот звонок для вас. Если вы пишете свою собственную функцию `DoFieldExchange` и используете мастера для написания функции, добавляйте вызовы к своей собственной функции за пределами карты поля. Если вы не используете мастера, не будет карты поля. Вызов предшествует вызовам к функциям DFX, по одному для каждого члена `CDaoFieldExchange::outputColumn`данных вашего класса, и определяет тип поля как .

Если вы параметризируете свой класс рекордных наборов, следует добавить DFX-звонки для всех `SetFieldType`параметров данных (за пределами карты поля) и предшествовать этим вызовам с вызовом. Передайте `CDaoFieldExchange::param`значение. (Вместо этого можно использовать [CDao-EryDef](../../mfc/reference/cdaoquerydef-class.md) и устанавливать значения параметров.)

Как правило, каждой группе вызовов функции DFX, связанных с `SetFieldType`членами данных на местах или членами параметров, должен предшествовать вызов. Параметр *nFieldType* `SetFieldType` каждого вызова определяет тип данных членов, представленных вызовами `SetFieldType` функции DFX, которые следуют за вызовом.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset класс](../../mfc/reference/cdaorecordset-class.md)
