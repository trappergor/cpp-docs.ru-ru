---
title: Класс Кфиелдексчанже
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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425901"
---
# <a name="cfieldexchange-class"></a>Класс Кфиелдексчанже

Поддерживает процедуры обмена полями записей (RFX) и блочного обмена полями записей (Bulk RFX), используемые классами баз данных.

## <a name="syntax"></a>Синтаксис

```
class CFieldExchange
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кфиелдексчанже:: Исфиелдтипе](#isfieldtype)|Возвращает ненулевое значение, если текущая операция подходит для типа обновляемого поля.|
|[Кфиелдексчанже:: Сетфиелдтипе](#setfieldtype)|Указывает тип элемента данных набора записей — столбец или параметр, представленный всеми вызовами функций RFX до следующего вызова `SetFieldType`.|

## <a name="remarks"></a>Remarks

`CFieldExchange` не имеет базового класса.

Этот класс используется при написании подпрограмм обмена данными для пользовательских типов данных или при реализации групповой выборки строк. в противном случае вы не будете использовать этот класс напрямую. RFX и групповые RFX обмениваются данными между элементами данных поля объекта Recordset и соответствующими полями текущей записи в источнике данных.

> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO), а не с классами ODBC, используйте вместо этого класс [кдаофиелдексчанже](../../mfc/reference/cdaofieldexchange-class.md) . Дополнительные сведения см. в статье [Общие сведения о программировании баз данных](../../data/data-access-programming-mfc-atl.md).

Объект `CFieldExchange` предоставляет контекстную информацию, необходимую для обмена полями записей или обмена полями с массовыми записями. `CFieldExchange` объекты поддерживают ряд операций, включая параметры привязки и элементы данных полей, а также задание различных флагов для полей текущей записи. Операции RFX и массовых RFX выполняются для членов данных класса набора записей типов, определенных **перечислением** **FieldType** в `CFieldExchange`. Возможные значения **FieldType** :

- `CFieldExchange::outputColumn` для элементов данных полей.

- `CFieldExchange::inputParam` или `CFieldExchange::param` для элементов данных входных параметров.

- `CFieldExchange::outputParam` для элементов данных выходных параметров.

- `CFieldExchange::inoutParam` для элементов данных входных и выходных параметров.

Большинство функций и элементов данных класса предоставляются для написания собственных пользовательских подпрограмм RFX. Вы будете использовать `SetFieldType` часто. Дополнительные сведения см. в статьях, посвященных [обмену полями записей (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [набором записей (ODBC)](../../data/odbc/recordset-odbc.md). Дополнительные сведения о групповой выборке строк см. в статье [набор записей: некоторая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения о глобальных функциях RFX и групповой RFX см. в разделе [функции обмена полями записи](../../mfc/reference/record-field-exchange-functions.md) раздела макросы и глобальные классы MFC этой ссылки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CFieldExchange`

## <a name="requirements"></a>Требования

**Заголовок:** афксдб. h

##  <a name="isfieldtype"></a>Кфиелдексчанже:: Исфиелдтипе

При написании собственной функции RFX вызовите `IsFieldType` в начале функции, чтобы определить, можно ли выполнить текущую операцию с определенным типом элемента данных поля или параметра (`CFieldExchange::outputColumn`, `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`или `CFieldExchange::inoutParam`).

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>Параметры

*пнфиелд*<br/>
В этом параметре возвращается порядковый номер элемента данных поля или параметра. Это число соответствует порядку элементов данных в функции [CRecordset::D офиелдексчанже](../../mfc/reference/crecordset-class.md#dofieldexchange) или [CRecordset::D обулкфиелдексчанже](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) .

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если текущая операция может быть выполнена с текущим полем или типом параметра.

### <a name="remarks"></a>Remarks

Используйте модель существующих функций RFX.

##  <a name="setfieldtype"></a>Кфиелдексчанже:: Сетфиелдтипе

Необходимо вызвать `SetFieldType` в переопределении функции [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) или [добулкфиелдексчанже](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) класса Recordset.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Параметры

*нфиелдтипе*<br/>
Значение `enum FieldType`, объявленное в `CFieldExchange`, может быть одним из следующих:

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>Remarks

Для элементов данных полей необходимо вызвать `SetFieldType` с параметром `CFieldExchange::outputColumn`, а затем вызовами функций RFX или Массовы. Если вы не реализовали многострочную выборку строк, ClassWizard поместит этот `SetFieldType` вызов в разделе "Таблица соответствия полей" `DoFieldExchange`.

При параметризации класса набора записей необходимо вызвать `SetFieldType` снова, за пределами раздела с картой полей, за которым следуют вызовы RFX для всех элементов данных параметров. Каждый тип члена данных параметра должен иметь собственный вызов `SetFieldType`. В следующей таблице представлены различные значения, которые можно передать в `SetFieldType` для представления членов данных параметра класса:

|Значение параметра Сетфиелдтипе|Тип элемента данных параметра|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|Входной параметр. Значение, передаваемое в запрос или хранимую процедуру набора записей.|
|`CFieldExchange::param` | то же, что и `CFieldExchange::inputParam`.|
|`CFieldExchange::outputParam`|Выходной параметр. Возвращаемое значение хранимой процедуры набора записей.|
|`CFieldExchange::inoutParam`|Входной/выходной параметр. Значение, которое передается и возвращается из хранимой процедуры набора записей.|

В общем случае каждой группе вызовов функций RFX, связанных с элементами данных полей или элементами данных параметров, должен предшествовать вызов `SetFieldType`. Параметр *нфиелдтипе* каждого вызова `SetFieldType` идентифицирует тип элементов данных, представленных вызовами функций RFX, которые следуют за вызовом `SetFieldType`.

Дополнительные сведения об обработке выходных данных и параметров ввода-вывода см. в описании функции-члена `CRecordset` [флушресултсет](../../mfc/reference/crecordset-class.md#flushresultset). Дополнительные сведения о функциях RFX и Массовы RFX см. в разделе [функции обмена полями записи](../../mfc/reference/record-field-exchange-functions.md). Дополнительные сведения о групповой выборке строк см. в статье [набор записей: некоторая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

В этом примере показано несколько вызовов функций RFX с сопутствующими вызовами для `SetFieldType`. Обратите внимание, что `SetFieldType` вызывается через `pFX` указатель на объект `CFieldExchange`.

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
