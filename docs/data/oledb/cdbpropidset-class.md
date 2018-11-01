---
title: Класс CDBPropIDSet
ms.date: 11/04/2016
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
ms.openlocfilehash: b6e7208628ee77df8647eaa46b00e6e22d294879
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529146"
---
# <a name="cdbpropidset-class"></a>Класс CDBPropIDSet

Наследует от `DBPROPIDSET` структурировать и добавляет конструктор, который инициализирует ключевых полей, а также [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) доступ к методу.

## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[AddPropertyID](#addpropertyid)|Добавляет свойство в набор свойств идентификатора.|
|[CDBPropIDSet](#cdbpropidset)|Конструктор.|
|[SetGUID](#setguid)|Задает идентификатор GUID набора.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор =](#op_equal)|Назначает содержимого идентификатор свойства набора в другой.|

## <a name="remarks"></a>Примечания

Использования потребителей OLE DB `DBPROPIDSET` структуры передается массив идентификаторов свойств, для которых необходимо получить сведения о свойстве. Свойств, идентифицированных в одном [DBPROPIDSET](/previous-versions/windows/desktop/ms717981) структура принадлежат набору одно свойство.

## <a name="addpropertyid"></a> CDBPropIDSet::AddPropertyID

Добавляет идентификатор свойства идентификатор набора свойств.

### <a name="syntax"></a>Синтаксис

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>Параметры

*PropID*<br/>
[in] Задайте идентификатор свойства, необходимо добавить идентификатор свойства.

## <a name="cdbpropidset"></a> CDBPropIDSet::CDBPropIDSet

Конструктор. Инициализирует `rgProperties`, `cProperties`и (необязательно) `guidPropertySet` поля [DBPROPIDSET](/previous-versions/windows/desktop/ms717981) структуры.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>Параметры

*Идентификатор GUID*<br/>
[in] Идентификатор GUID, используемый для инициализации `guidPropertySet` поля.

*propidset*<br/>
[in] Другой `CDBPropIDSet` объект для копирования.

## <a name="setguid"></a> CDBPropIDSet::SetGUID

Задает GUID поля в `DBPROPIDSET` структуры.

### <a name="syntax"></a>Синтаксис

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Параметры

*Идентификатор GUID*<br/>
[in] Идентификатор GUID, используемый для задания `guidPropertySet` поле [DBPROPIDSET](/previous-versions/windows/desktop/ms717981) структуры.

### <a name="remarks"></a>Примечания

Это поле можно задать [конструктор](../../data/oledb/cdbpropidset-cdbpropidset.md) также. Эта функция вызывается в том случае, если вы используете конструктор по умолчанию для этого класса.

## <a name="op_equal"></a> CDBPropIDSet::operator =

Назначает содержимое задать другой набор свойств ID идентификатор свойства.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)