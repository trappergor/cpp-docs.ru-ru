---
title: Класс Ккомконтаинедобжект
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
ms.openlocfilehash: c5e2fa64cc0938e632a37eac7dd1d6e9111c3d98
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497323"
---
# <a name="ccomcontainedobject-class"></a>Класс Ккомконтаинедобжект

Этот класс реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , делегируя его объекту `IUnknown`Owner.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Параметры

*Из*<br/>
Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомконтаинедобжект:: Ккомконтаинедобжект](#ccomcontainedobject)|Конструктор. Инициализирует указатель элемента для объекта `IUnknown`владельца.|
|[Ккомконтаинедобжект:: ~ Ккомконтаинедобжект](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомконтаинедобжект:: AddRef](#addref)|Увеличивает значение счетчика ссылок на объекте Owner.|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Получает объект `IUnknown`владельца.|
|[Ккомконтаинедобжект:: QueryInterface](#queryinterface)|Извлекает указатель на интерфейс, запрошенный для объекта-владельца.|
|[Ккомконтаинедобжект:: Release](#release)|Уменьшает значение счетчика ссылок на объекте Owner.|

## <a name="remarks"></a>Примечания

ATL использует `CComContainedObject` в классах [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md)и [ккомкачедтеароффобжект](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , делегируя его объекту `IUnknown`Owner. (Владельцем является либо внешний объект агрегата, либо объект, для которого создается интерфейс разрыва.) `CComContainedObject` вызовы`CComObjectRootEx` ,`OuterRelease` и,`Base`все наследуются через. `OuterAddRef` `OuterQueryInterface`

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComContainedObject`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="addref"></a>Ккомконтаинедобжект:: AddRef

Увеличивает значение счетчика ссылок на объекте Owner.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

##  <a name="ccomcontainedobject"></a>Ккомконтаинедобжект:: Ккомконтаинедобжект

Конструктор.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
окне Объект `IUnknown`Owner.

### <a name="remarks"></a>Примечания

Устанавливает для указателя на `Base`член (наследуется через класс) значение ПС `m_pOuterUnknown` .

##  <a name="dtor"></a>Ккомконтаинедобжект:: ~ Ккомконтаинедобжект

Деструктор

```
~CComContainedObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="getcontrollingunknown"></a>Ккомконтаинедобжект:: Жетконтроллингункновн

Возвращает указатель `m_pOuterUnknown` на элемент (наследуется через *базовый* класс), который содержит объект `IUnknown`-владелец.

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `IUnknown`Owner.

### <a name="remarks"></a>Примечания

Этот метод может быть виртуальным `Base` , если объявлен макрос [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) .

##  <a name="queryinterface"></a>Ккомконтаинедобжект:: QueryInterface

Извлекает указатель на интерфейс, запрошенный для объекта-владельца.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по *IID*. Если объект не поддерживает этот интерфейс, *ппвобжект* имеет значение null.

*PP*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по типу `Q`. Если объект не поддерживает этот интерфейс, *PP* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="release"></a>Ккомконтаинедобжект:: Release

Уменьшает значение счетчика ссылок на объекте Owner.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В сборках, не относящихся к отладке, `Release` всегда возвращает 0.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
