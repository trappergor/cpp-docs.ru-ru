---
title: Класс IAccessorImpl
ms.date: 11/04/2016
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
ms.openlocfilehash: f1865089100ac7f60e8c011e72eedb3d0a3f8470
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545993"
---
# <a name="iaccessorimpl-class"></a>Класс IAccessorImpl

Предоставляет реализацию интерфейса [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T,
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс набора строк или командного объекта.

*биндтипе*<br/>
Единица хранения сведений о привязке. Значение по умолчанию — структура `ATLBINDINGS` (см. ATLDB. h).

*биндингвектор*<br/>
Единица хранения сведений о столбце. Значение по умолчанию — [CAtlMap](../../atl/reference/catlmap-class.md) , где элемент key является значением HACCESSOR, а элемент value — указателем на структуру `BindType`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[IAccessorImpl](#iaccessorimpl)|Конструктор.|

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[аддрефакцессор](#addrefaccessor)|Добавляет счетчик ссылок в существующий метод доступа.|
|[CreateAccessor](#createaccessor)|Создает метод доступа из набора привязок.|
|[Привязок](#getbindings)|Возвращает привязки из метода доступа.|
|[релеасеакцессор](#releaseaccessor)|Освобождает метод доступа.|

## <a name="remarks"></a>Примечания

Это обязательно для наборов строк и команд. OLE DB требует, чтобы поставщики реализовали HACCESSOR, который является тегом массива структур [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) . Хакцессорс, предоставляемый `IAccessorImpl`, являются адресами структур `BindType`. По умолчанию `BindType` определяется как `ATLBINDINGS` в определении шаблона `IAccessorImpl`. `BindType` предоставляет механизм, используемый `IAccessorImpl` для контроля количества элементов в его `DBBINDING` массиве, а также для счетчика ссылок и флагов доступа.

## <a name="iaccessorimpliaccessorimpl"></a><a name="iaccessorimpl"></a>IAccessorImpl:: IAccessorImpl

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
IAccessorImpl();
```

## <a name="iaccessorimpladdrefaccessor"></a><a name="addrefaccessor"></a>IAccessorImpl:: Аддрефакцессор

Добавляет счетчик ссылок в существующий метод доступа.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Параметры

См. раздел [IAccessor:: аддрефакцессор](/previous-versions/windows/desktop/ms714978(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="iaccessorimplcreateaccessor"></a><a name="createaccessor"></a>IAccessorImpl:: CreateAccessor

Создает метод доступа из набора привязок.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,
   DBCOUNTITEM cBindings,
   const DBBINDING rgBindings[],
   DBLENGTH cbRowSize,
   HACCESSOR* phAccessor,
   DBBINDSTATUS rgStatus[]);
```

#### <a name="parameters"></a>Параметры

См. раздел [IAccessor:: CreateAccessor](/previous-versions/windows/desktop/ms720969(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="iaccessorimplgetbindings"></a><a name="getbindings"></a>IAccessorImpl:: DataBindings

Возвращает привязки базовых столбцов от потребителя в методе доступа.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,
   DBACCESSORFLAGS* pdwAccessorFlags,
   DBCOUNTITEM* pcBindings,
   DBBINDING** prgBindings);
```

#### <a name="parameters"></a>Параметры

См. раздел [IAccessor:: DataBindings](/previous-versions/windows/desktop/ms721253(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="iaccessorimplreleaseaccessor"></a><a name="releaseaccessor"></a>IAccessorImpl:: Релеасеакцессор

Освобождает метод доступа.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Параметры

См. раздел [IAccessor:: релеасеакцессор](/previous-versions/windows/desktop/ms719717(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также:

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)