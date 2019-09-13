---
title: Класс Ккомобжектнолокк
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: 9253c7495f4d13ed6ce609988251d8abd09592ad
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497038"
---
# <a name="ccomobjectnolock-class"></a>Класс Ккомобжектнолокк

Этот класс реализует `IUnknown` для неагрегированного объекта, но не увеличивает счетчик блокировок модуля в конструкторе.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Параметры

*Из*<br/>
Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любого другого интерфейса, который требуется поддерживать для объекта.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Конструктор.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|Увеличивает значение счетчика ссылок на объект.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|Возвращает указатель на запрошенный интерфейс.|
|[CComObjectNoLock::Release](#release)|Уменьшает значение счетчика ссылок на объект.|

## <a name="remarks"></a>Примечания

`CComObjectNoLock`аналогичен [CComObject](../../atl/reference/ccomobject-class.md) в том, что он реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для неагрегированного объекта. `CComObjectNoLock` однако не увеличивает счетчик блокировок модуля в конструкторе.

В библиотеке `CComObjectNoLock` ATL используются внутренние фабрики классов. В общем случае этот класс не будет использоваться напрямую.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="addref"></a>  CComObjectNoLock::AddRef

Увеличивает значение счетчика ссылок на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock

Конструктор. В отличие от [CComObject](../../atl/reference/ccomobject-class.md), не увеличивает счетчик блокировок модуля.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Параметры

<em>void\*</em><br/>
окне Этот неименованный параметр не используется. Он существует для симметрии с `CComXXXObjectXXX` другими конструкторами.

##  <a name="dtor"></a>  CComObjectNoLock::~CComObjectNoLock

Деструктор

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызывает [финалрелеасе](ccomobjectrootex-class.md#finalrelease).

##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по *IID*. Если объект не поддерживает этот интерфейс, *ппвобжект* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="release"></a>  CComObjectNoLock::Release

Уменьшает значение счетчика ссылок на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В сборках, не относящихся к отладке, `Release` всегда возвращает 0.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
