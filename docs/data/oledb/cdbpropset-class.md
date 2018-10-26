---
title: Класс CDBPropSet | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
- CDBPropSet.CDBPropSet
- CDBPropSet::CDBPropSet
- ATL::CDBPropSet::CDBPropSet
- ATL.CDBPropSet.CDBPropSet
- CDBPropSet.operator=
- ATL::CDBPropSet::operator=
- ATL.CDBPropSet.operator=
- CDBPropSet::operator=
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class
- AddProperty method
- CDBPropSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
- AddProperty method
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a047416c22eb57fc3ee3d3eb6a69275768182525
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081905"
---
# <a name="cdbpropset-class"></a>Класс CDBPropSet

Наследует от `DBPROPSET` структурировать и добавляет конструктор, который инициализирует ключевых полей, а также `AddProperty` доступ к методу.

## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[AddProperty](#addproperty)|Добавляет свойство в набор свойств.|
|[CDBPropSet](#cdbpropset)|Конструктор.|
|[SetGUID](#setguid)|Наборы `guidPropertySet` поле `DBPROPSET` структуры.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[оператор =](#op_equal)|Назначает содержимое для одного свойства.|

## <a name="remarks"></a>Примечания

Использование поставщиков и потребителей OLE DB `DBPROPSET` структуры для передачи массивов `DBPROP` структуры. Каждый `DBPROP` структура представляет одно свойство, которое можно задать.

## <a name="addproperty"></a> CDBPropSet::AddProperty

Добавляет свойство в набор свойств.

### <a name="syntax"></a>Синтаксис

```cpp
bool AddProperty(DWORD dwPropertyID, 
   constVARIANT& var, 
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();
```

#### <a name="parameters"></a>Параметры

*dwPropertyID*<br/>
[in] Идентификатор добавляемого свойства. Используется для инициализации `dwPropertyID` из `DBPROP` структуры, добавляемый в набор свойств.

*var*<br/>
[in] Значение variant, используемый для инициализации значение свойства для `DBPROP` структуры, добавляемый в набор свойств.

*szValue*<br/>
[in] Строка, используемая для инициализации значения свойства для `DBPROP` структуры, добавляемый в набор свойств.

*bValue*<br/>
[in] Объект `BYTE` или логическое значение, используемое для инициализации значения свойства для `DBPROP` структуры, добавляемый в набор свойств.

*nValue*<br/>
[in] Целочисленное значение, используемое для инициализации значение свойства для `DBPROP` структуры, добавляемый в набор свойств.

*fltValue*<br/>
[in] Значение с плавающей запятой, используемый для инициализации значение свойства для `DBPROP` структуры, добавляемый в набор свойств.

*dblValue*<br/>
[in] Значение с плавающей запятой двойной точности, используемый для инициализации значение свойства для `DBPROP` структуры, добавляемый в набор свойств.

*cyValue*<br/>
[in] Значение валюты CY, используемый для инициализации значение свойства для `DBPROP` структуры, добавляемый в набор свойств.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если свойство было успешно добавлено. В противном случае **false**.

## <a name="cdbpropset"></a> CDBPropSet::CDBPropSet

Конструктор. Инициализирует `rgProperties`, `cProperties`, и `guidPropertySet` поля [DBPROPSET](/previous-versions/windows/desktop/ms714367) структуры.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>Параметры

*Идентификатор GUID*<br/>
[in] Идентификатор GUID, используемый для инициализации `guidPropertySet` поля.

*набор свойств*<br/>
[in] Другой `CDBPropSet` объект для копирования.

## <a name="setguid"></a> CDBPropSet::SetGUID

Наборы `guidPropertySet` в `DBPROPSET` структуры.

### <a name="syntax"></a>Синтаксис

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Параметры

*Идентификатор GUID*<br/>
[in] Идентификатор GUID, используемый для задания `guidPropertySet` поле [DBPROPSET](/previous-versions/windows/desktop/ms714367) структуры.

### <a name="remarks"></a>Примечания

Это поле можно задать [конструктор](../../data/oledb/cdbpropset-cdbpropset.md) также.

## <a name="op_equal"></a> CDBPropSet::operator =

Назначает содержимое одного из свойств задать другой набор свойств.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)<br/>
[Структуре DBPROPSET](/previous-versions/windows/desktop/ms714367)
[структуры DBPROP](/previous-versions/windows/desktop/ms717970)