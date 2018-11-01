---
title: Класс CComContainedObject
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 289174fbfc61b0bbca65233fe24d93537627e17d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492577"
---
# <a name="ccomcontainedobject-class"></a>Класс CComContainedObject

Этот класс реализует [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) делегируя владельца объекта `IUnknown`.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Параметры

*Base*<br/>
Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Конструктор. Инициализирует элемент указатель на объект владельца `IUnknown`.|
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComContainedObject::AddRef](#addref)|Увеличивает счетчик ссылок на объект владельца.|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Извлекает объект владельца `IUnknown`.|
|[CComContainedObject::QueryInterface](#queryinterface)|Извлекает указатель на интерфейс, запрошенный в объекте владельца.|
|[CComContainedObject::Release](#release)|Уменьшает счетчик ссылок на объект владельца.|

## <a name="remarks"></a>Примечания

Использует ATL `CComContainedObject` в классах [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), и [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject` реализует [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) делегируя владельца объекта `IUnknown`. (Им является внешний объект статистической обработки, или объект, для которого создается интерфейсом перемещаемой.) `CComContainedObject` вызовы `CComObjectRootEx` `OuterQueryInterface`, `OuterAddRef`, и `OuterRelease`, наследуемых через `Base`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComContainedObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="addref"></a>  CComContainedObject::AddRef

Увеличивает счетчик ссылок на объект владельца.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

##  <a name="ccomcontainedobject"></a>  CComContainedObject::CComContainedObject

Конструктор.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
[in] Владелец объекта `IUnknown`.

### <a name="remarks"></a>Примечания

Наборы `m_pOuterUnknown` указателя на член (унаследованные `Base` класс) для *pv*.

##  <a name="dtor"></a>  CComContainedObject:: ~ CComContainedObject

Деструктор

```
~CComContainedObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="getcontrollingunknown"></a>  CComContainedObject::GetControllingUnknown

Возвращает `m_pOuterUnknown` указателя на член (унаследованные *базы* класс), содержащий объект владельца `IUnknown`.

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Владелец объекта `IUnknown`.

### <a name="remarks"></a>Примечания

Этот метод может быть виртуальной Если `Base` объявило [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) макрос.

##  <a name="queryinterface"></a>  CComContainedObject::QueryInterface

Извлекает указатель на интерфейс, запрошенный в объекте владельца.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор запрашиваемого интерфейса.

*ppvObject*<br/>
[out] Указатель на указатель интерфейса, идентифицируемый *iid*. Если объект не поддерживает этот интерфейс *ppvObject* имеет значение NULL.

*PP*<br/>
[out] Указатель на указатель интерфейса, идентифицируемый по типу `Q`. Если объект не поддерживает этот интерфейс *pp* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="release"></a>  CComContainedObject::Release

Уменьшает счетчик ссылок на объект владельца.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В неотладочных сборках `Release` всегда возвращает значение 0.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
