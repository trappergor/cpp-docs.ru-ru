---
title: Класс CDBPropSet
ms.date: 11/04/2016
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
- CDBPropSet::SetGUID
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
ms.openlocfilehash: 08cab967fbfbd4b3207e96a4fdbd2d2dbc6da793
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79546119"
---
# <a name="cdbpropset-class"></a>Класс CDBPropSet

Наследует от структуры `DBPROPSET` и добавляет конструктор, который инициализирует ключевые поля, а также метод доступа `AddProperty`.

## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropSet : public tagDBPROPSET
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[AddProperty](#addproperty)|Добавляет свойство в набор свойств.|
|[кдбпропсет](#cdbpropset)|Конструктор.|
|[сетгуид](#setguid)|Задает поле `guidPropertySet` структуры `DBPROPSET`.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](#op_equal)|Присваивает содержимому одного свойства значение другого.|

## <a name="remarks"></a>Примечания

Поставщики OLE DB и потребители используют структуры `DBPROPSET` для передачи массивов структур `DBPROP`. Каждая структура `DBPROP` представляет одно свойство, которое можно задать.

## <a name="cdbpropsetaddproperty"></a><a name="addproperty"></a>Кдбпропсет:: AddProperty

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

*двпропертид*<br/>
окне Идентификатор добавляемого свойства. Используется для инициализации `dwPropertyID` структуры `DBPROP`, добавленной в набор свойств.

*var*<br/>
окне Вариант, используемый для инициализации значения свойства для структуры `DBPROP`, добавленной в набор свойств.

*сзвалуе*<br/>
окне Строка, используемая для инициализации значения свойства для структуры `DBPROP`, добавленной в набор свойств.

*bValue*<br/>
окне `BYTE` или логическое значение, используемое для инициализации значения свойства для структуры `DBPROP`, добавленной в набор свойств.

*Nзначение*<br/>
окне Целочисленное значение, используемое для инициализации значения свойства для структуры `DBPROP`, добавленной в набор свойств.

*флтвалуе*<br/>
окне Значение с плавающей запятой, используемое для инициализации значения свойства для структуры `DBPROP`, добавленной в набор свойств.

*дблвалуе*<br/>
окне Значение с плавающей запятой двойной точности, используемое для инициализации значения свойства для структуры `DBPROP`, добавленной в набор свойств.

*цивалуе*<br/>
окне Значение валюты CY, используемое для инициализации значения свойства для структуры `DBPROP`, добавленной в набор свойств.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если свойство было успешно добавлено. В противном случае — **false**.

## <a name="cdbpropsetcdbpropset"></a><a name="cdbpropset"></a>Кдбпропсет:: Кдбпропсет

Конструктор. Инициализирует поля `rgProperties`, `cProperties`и `guidPropertySet` структуры [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) .

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropSet(const GUID& guid);

CDBPropSet(const CDBPropSet& propset);

CDBPropSet();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для инициализации поля `guidPropertySet`.

*Prop*<br/>
окне Другой объект `CDBPropSet` для создания копии.

## <a name="cdbpropsetsetguid"></a><a name="setguid"></a>Кдбпропсет:: Сетгуид

Задает поле `guidPropertySet` в структуре `DBPROPSET`.

### <a name="syntax"></a>Синтаксис

```cpp
void SetGUID(const GUID& guid) throw();
```

#### <a name="parameters"></a>Параметры

*guid*<br/>
окне Идентификатор GUID, используемый для задания `guidPropertySet` поля структуры [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) .

### <a name="remarks"></a>Примечания

Это поле также может быть задано [конструктором](../../data/oledb/cdbpropset-cdbpropset.md) .

## <a name="cdbpropsetoperator-"></a><a name="op_equal"></a>Кдбпропсет:: operator =

Присваивает содержимое одного свойства набору другому набору свойств.

### <a name="syntax"></a>Синтаксис

```cpp
CDBPropSet& operator =(CDBPropSet& propset) throw();
```

## <a name="see-also"></a>См. также:

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)<br/>
Структура [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))
[DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85))