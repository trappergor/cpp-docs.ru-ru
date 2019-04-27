---
title: Класс CComObjectNoLock
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
ms.openlocfilehash: 50dc4505c1da8df9efc0c9d0028461ef49c0840e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246304"
---
# <a name="ccomobjectnolock-class"></a>Класс CComObjectNoLock

Этот класс реализует `IUnknown` для неагрегированные объекта, но не не инкремента, счетчик блокировок модуля в конструкторе.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>Параметры

*Base*<br/>
Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также как и из любого другого интерфейса, которые должны поддерживаться в объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Конструктор.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|Увеличивает счетчик ссылок на объект.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|Возвращает указатель на запрашиваемый интерфейс.|
|[CComObjectNoLock::Release](#release)|Уменьшает счетчик ссылок на объект.|

## <a name="remarks"></a>Примечания

`CComObjectNoLock` аналогичен [CComObject](../../atl/reference/ccomobject-class.md) тем, что он реализует [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) для объекта неагрегированные; тем не менее, `CComObjectNoLock` выполняет подсчет приращения блокировки модуля в конструкторе.

ATL использует `CComObjectNoLock` для фабрик классов. Как правило вы не будет использовать этот класс напрямую.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="addref"></a>  CComObjectNoLock::AddRef

Увеличивает счетчик ссылок на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock

Конструктор. В отличие от [CComObject](../../atl/reference/ccomobject-class.md), не увеличивает счетчик блокировки модуля.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>Параметры

<em>void\*</em><br/>
[in] Этот параметр без имени не используется. Он существует для согласованности с другими `CComXXXObjectXXX` конструкторы.

##  <a name="dtor"></a>  CComObjectNoLock::~CComObjectNoLock

Деструктор

```
~CComObjectNoLock();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызовы [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор запрашиваемого интерфейса.

*ppvObject*<br/>
[out] Указатель на указатель интерфейса, идентифицируемый *iid*. Если объект не поддерживает этот интерфейс *ppvObject* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="release"></a>  CComObjectNoLock::Release

Уменьшает счетчик ссылок на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В неотладочных сборках `Release` всегда возвращает значение 0.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
