---
title: Класс CFieldExchange
ms.date: 11/04/2016
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
ms.openlocfilehash: d4b99a4992075072253d4f9b3182a926673bdfd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373931"
---
# <a name="cfieldexchange-class"></a>Класс CFieldExchange

Поддерживает процедуры обмена полями записей (RFX) и блочного обмена полями записей (Bulk RFX), используемые классами баз данных.

## <a name="syntax"></a>Синтаксис

```
class CFieldExchange
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFieldExchange::IsFieldType](#isfieldtype)|Возвращает ненулевой, если текущая операция подходит для типа обновления поля.|
|[CFieldExchange::SetFieldType](#setfieldtype)|Опосредочен тип члена данных записей - столбца или параметра - представленного `SetFieldType`всеми следующими вызовами к функциям RFX до следующего вызова.|

## <a name="remarks"></a>Remarks

`CFieldExchange`не имеет базового класса.

Используйте этот класс, если вы пишете процедуры обмена данными для пользовательских типов данных или когда вы реализуете объем строки извлечения; в противном случае вы не будете непосредственно использовать этот класс. RFX и Bulk RFX обмениваются данными между полевыми данными вашего объекта записи и соответствующими полями текущей записи источника данных.

> [!NOTE]
> Если вы работаете с классами объектов доступа к данным (DAO), а не с классами Open Database Connectivity (ODBC), используйте класс [CDaoFieldExchange.](../../mfc/reference/cdaofieldexchange-class.md) Для получения дополнительной информации смотрите статью [Обзор: Программирование баз данных](../../data/data-access-programming-mfc-atl.md).

Объект `CFieldExchange` предоставляет контекстную информацию, необходимую для обмена полями записей или обмена объемными данными. `CFieldExchange`объекты поддерживают ряд операций, включая параметры связывания и составы полевых данных и установку различных флагов на полях текущей записи. Операции RFX и Bulk RFX выполняются на данных регистраторов типов, `CFieldExchange`определенных **enum** **FieldType** в . Возможные значения **FieldType:**

- `CFieldExchange::outputColumn`для членов полевых данных.

- `CFieldExchange::inputParam`или `CFieldExchange::param` для членов данных ввода.

- `CFieldExchange::outputParam`для членов данных параметров вывода.

- `CFieldExchange::inoutParam`для членов параметров ввода/вывода.

Большинство функций членов класса и членов данных предоставляются для написания собственных пользовательских процедур RFX. Вы будете `SetFieldType` использовать часто. Для получения дополнительной информации смотрите статьи [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [Recordset (ODBC).](../../data/odbc/recordset-odbc.md) Для получения информации о объемных [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)строк извлечения, см. Подробнее о глобальных функциях RFX и Bulk RFX [можно](../../mfc/reference/record-field-exchange-functions.md) узнать в разделе MFC Macros and Globals в разделе этой справки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CFieldExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a>CFieldExchange::IsFieldType

Если вы пишете свою собственную функцию RFX, позвоните `IsFieldType` в начале функции, чтобы определить, `CFieldExchange::outputColumn`может `CFieldExchange::inputParam` `CFieldExchange::param`ли `CFieldExchange::outputParam`текущая операция быть выполнена на определенном поле или типе данных параметра (a, , , или `CFieldExchange::inoutParam`).

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>Параметры

*pnField*<br/>
Последовательное число члена данных поля или параметра возвращается в этом параметре. Это число соответствует заказу участника данных в функции [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [CRecordset::DoBulkFieldExchange.](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если текущая операция может быть выполнена на текущем поле или типе параметра.

### <a name="remarks"></a>Remarks

Следуйте модели существующих функций RFX.

## <a name="cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a>CFieldExchange::SetFieldType

Вам нужен `SetFieldType` звонок в [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) вашего класса recordset.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Параметры

*nFieldType*<br/>
Значение `enum FieldType`, объявлено `CFieldExchange`в , который может быть одним из следующих:

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>Remarks

Для членов полевых данных необходимо `SetFieldType` `CFieldExchange::outputColumn`звонить с параметром, за которым следуют вызовы на функции RFX или Bulk RFX. Если вы не реализовали объем строки извлечения, то ClassWizard места этот `SetFieldType` вызов для вас в разделе карты поля `DoFieldExchange`.

Если вы параметризируете свой `SetFieldType` класс рекордных наборов, вы должны позвонить снова, вне любого раздела карты поля, а затем RFX призывает всех членов параметров данных. Каждый тип параметра данных `SetFieldType` член должен иметь свой собственный вызов. В следующей таблице различается различные значения, которые можно передать `SetFieldType` для представления параметров данных членов вашего класса:

|Значение параметра SetFieldType|Тип члена параметра|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|Входной параметр. Значение, передаваемые в процедуру запроса или сохранения записи.|
|`CFieldExchange::param` | так `CFieldExchange::inputParam`же, как .|
|`CFieldExchange::outputParam`|Выходной параметр. Значение возврата процедуры хранения рекорда.|
|`CFieldExchange::inoutParam`|Параметр ввода/вывода. Значение, которое передается и возвращается из процедуры хранения записи.|

Как правило, каждой группе вызовов функции RFX, связанных с `SetFieldType`членами данных на местах или членами параметров, должен предшествовать вызов. Параметр *nFieldType* `SetFieldType` каждого вызова определяет тип членов данных, представленных вызовами `SetFieldType` функции RFX, которые следуют за вызовом.

Для получения дополнительной информации об обработке выходных `CRecordset` и вводимых /выходных параметров см. [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset) Для получения дополнительной информации о функциях RFX [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md)и Bulk RFX см. Для соответствующей информации о объемных [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)строк извлечения, см.

### <a name="example"></a>Пример

В этом примере показано несколько вызовов `SetFieldType`функций RFX с сопутствующими вызовами. Обратите `SetFieldType` внимание, что `pFX` вызывается `CFieldExchange` через указатель на объект.

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
