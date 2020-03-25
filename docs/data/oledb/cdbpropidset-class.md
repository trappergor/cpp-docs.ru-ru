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
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
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
ms.openlocfilehash: a52d7443ab335e8546a4bcce03cf68c3b1d60e3d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212039"
---
# <a name="cdbpropidset-class"></a>Класс CDBPropIDSet

Наследует от структуры `DBPROPIDSET` и добавляет конструктор, который инициализирует ключевые поля, а также метод доступа [аддпропертид](../../data/oledb/cdbpropidset-addpropertyid.md) .

## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropIDSet : public tagDBPROPIDSET
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[аддпропертид](#addpropertyid)|Добавляет свойство в набор ИДЕНТИФИКАТОРов свойств.|
|[кдбпропидсет](#cdbpropidset)|Конструктор.|
|[сетгуид](#setguid)|Задает идентификатор GUID для набора ИДЕНТИФИКАТОРов свойств.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](#op_equal)|Присваивает содержимому одного идентификатора свойства другое значение.|

## <a name="remarks"></a>Remarks

OLE DB потребители используют структуры `DBPROPIDSET` для передачи массива идентификаторов свойств, для которых потребитель хочет получить сведения о свойствах. Свойства, определенные в одной структуре [дбпропидсет](/previous-versions/windows/desktop/ms717981(v=vs.85)) , принадлежат одному набору свойств.

## <a name="cdbpropidsetaddpropertyid"></a><a name="addpropertyid"></a>Кдбпропидсет:: Аддпропертид

Добавляет идентификатор свойства в набор ИДЕНТИФИКАТОРов свойств.

### <a name="syntax"></a>Синтаксис

```cpp
bool AddPropertyID(DBPROPID propid) throw();
```

#### <a name="parameters"></a>Параметры

*PropID*<br/>
окне Идентификатор свойства, добавляемого к набору ИДЕНТИФИКАТОРов свойств.

## <a name="cdbpropidsetcdbpropidset"></a><a name="cdbpropidset"></a>Кдбпропидсет:: Кдбпропидсет

Конструктор. Инициализирует `rgProperties`, `cProperties`и (необязательно) `guidPropertySet` поля структуры [дбпропидсет](/previous-versions/windows/desktop/ms717981(v=vs.85)) .

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropIDSet(const GUID& guid);

CDBPropIDSet(const CDBPropIDSet& propidset);

CDBPropIDSet();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для инициализации поля `guidPropertySet`.

*пропидсет*<br/>
окне Другой объект `CDBPropIDSet` для создания копии.

## <a name="cdbpropidsetsetguid"></a><a name="setguid"></a>Кдбпропидсет:: Сетгуид

Задает поле GUID в структуре `DBPROPIDSET`.

### <a name="syntax"></a>Синтаксис

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для задания `guidPropertySet` поля структуры [дбпропидсет](/previous-versions/windows/desktop/ms717981(v=vs.85)) .

### <a name="remarks"></a>Remarks

Это поле также может быть задано [конструктором](../../data/oledb/cdbpropidset-cdbpropidset.md) . Вызывайте эту функцию, если для этого класса используется конструктор по умолчанию.

## <a name="cdbpropidsetoperator-"></a><a name="op_equal"></a>Кдбпропидсет:: operator =

Присваивает содержимому одного идентификатора свойства значение другого набора свойств ID.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();
```

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
