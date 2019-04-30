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
ms.openlocfilehash: e66b3ed16d4f21d46567c37bfaf7929d32f63b8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346357"
---
# <a name="cfieldexchange-class"></a>Класс CFieldExchange

Поддерживает процедуры обмена полями записей (RFX) и блочного обмена полями записей (Bulk RFX), используемые классами баз данных.

## <a name="syntax"></a>Синтаксис

```
class CFieldExchange
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CFieldExchange::IsFieldType](#isfieldtype)|Возвращает ненулевое значение, если текущая операция, соответствующие тип обновляемого поля.|
|[CFieldExchange::SetFieldType](#setfieldtype)|Указывает тип элемента данных набора записей — столбца или параметра, представленного всех следующих вызовов функций RFX до следующего вызова `SetFieldType`.|

## <a name="remarks"></a>Примечания

`CFieldExchange` не имеет базового класса.

Этот класс используется при создании процедуры данных exchange для пользовательских типов данных или при реализации массовой выборке строк; в противном случае вы не будет использовать непосредственно этот класс. RFX и Bulk RFX обеспечивает обмен данными между элементами данных полей объекта набора записей и соответствующих полях текущей записи в источнике данных.

> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO) вместо классов Open Database Connectivity (ODBC), используйте класс [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) вместо этого. Дополнительные сведения см. в статье [программирования Обзор: база данных](../../data/data-access-programming-mfc-atl.md).

Объект `CFieldExchange` предоставляет сведения о контексте требуется обмен полями записей или блочный обмен полей записей, чтобы воспользоваться поместить. `CFieldExchange` объекты поддерживают ряд операций, включая параметры привязки и поля элементов данных, а также установка различных флагов для полей текущей записи. RFX и Bulk RFX операции выполняются в членах данных набора записей класса типов, определенных **перечисления** **FieldType** в `CFieldExchange`. Возможные **FieldType** значения:

- `CFieldExchange::outputColumn` для поля элементов данных.

- `CFieldExchange::inputParam` или `CFieldExchange::param` для членов данных входного параметра.

- `CFieldExchange::outputParam` для вывода параметризованные члены данных.

- `CFieldExchange::inoutParam` для элементов данных параметров ввода вывода.

Большинство членов класса члена функции и данные предоставляются для написания собственные подпрограммы RFX. Вы воспользуетесь `SetFieldType` часто. Дополнительные сведения см. в статьях [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [записей (ODBC)](../../data/odbc/recordset-odbc.md). Сведения о массовой выборке строк см. в статье [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения о глобальных функций RFX и Bulk RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md) в разделе макросов MFC и глобальные объекты этой ссылки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CFieldExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

##  <a name="isfieldtype"></a>  CFieldExchange::IsFieldType

При написании собственной функции RFX, вызовите `IsFieldType` в начале функцию таким образом, чтобы определить, выполнение текущей операции для конкретного поля или параметра типа данных, член ( `CFieldExchange::outputColumn`, `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`, или `CFieldExchange::inoutParam`).

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>Параметры

*pnField*<br/>
В этом параметре возвращается последовательный номер элемента данных поля или параметра. Этот номер соответствует порядку элемент данных в [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) функции.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если текущая операция может выполняться для текущего типа поля или параметра.

### <a name="remarks"></a>Примечания

Следуйте модели для существующих функций RFX.

##  <a name="setfieldtype"></a>  CFieldExchange::SetFieldType

Требуется вызов `SetFieldType` в классе записей [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) переопределить.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Параметры

*nFieldType*<br/>
Значение `enum FieldType`, объявленные в `CFieldExchange`, который может принимать одно из следующих:

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>Примечания

Для поля элементов данных, необходимо вызвать `SetFieldType` с параметром `CFieldExchange::outputColumn`, а затем вызовов функций RFX и Bulk RFX. Если вы не реализовали выборка строк, то ClassWizard помещает это `SetFieldType` вызова для вас в разделе сопоставления поля `DoFieldExchange`.

Если вы параметризовать класса набора записей, необходимо вызвать `SetFieldType` опять же, за пределами раздела карты любого поля, после чего выполняется RFX вызовов для всех элементов данных параметра. Каждый тип члена данных параметра должно иметь свой собственный `SetFieldType` вызова. Следующая таблица различает разные значения, можно передать `SetFieldType` для представления параметризованные члены данных класса:

|Значение параметра SetFieldType|Тип элемента данных параметра|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|Входной параметр. Значение, которое было передано в запрос или хранимую процедуру набора записей.|
|`CFieldExchange::param` | Совпадение с кодом `CFieldExchange::inputParam`.|
|`CFieldExchange::outputParam`|Выходной параметр. Возвращаемое значение хранимой процедуры набора записей.|
|`CFieldExchange::inoutParam`|Параметр ввода вывода. Значение, которое передается в и возвращаемым из хранимой процедуры набора записей.|

Как правило, каждая группа функции RFX, связанные с элементами данных полей или членов данных параметра должен предшествовать вызов `SetFieldType`. *NFieldType* параметр каждого `SetFieldType` вызова определяет тип элементы данных, представленные функции RFX последующих `SetFieldType` вызова.

Дополнительные сведения об обработке выходных данных и входных и выходных параметров, см. в разделе `CRecordset` функция-член [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). Дополнительные сведения о функции RFX и Bulk RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md). Дополнительные сведения о массовой выборке строк см. в статье [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

В этом примере показано несколько вызовов функции RFX с сопутствующими вызовы `SetFieldType`. Обратите внимание, что `SetFieldType` вызывается через `pFX` указатель на `CFieldExchange` объект.

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
