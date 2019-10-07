---
title: Класс Ккомкачедтеароффобжект
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: d993a349d38342bda30a83dfdbe25577953799b3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497541"
---
# <a name="ccomcachedtearoffobject-class"></a>Класс Ккомкачедтеароффобжект

Этот класс реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для интерфейса разрыва.

## <a name="syntax"></a>Синтаксис

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Параметры

*нем*<br/>
Класс отрыва, производный от `CComTearOffObjectBase` , и интерфейсы, которые должен поддерживать ваш объект отрыва.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомкачедтеароффобжект:: Ккомкачедтеароффобжект](#ccomcachedtearoffobject)|Конструктор.|
|[Ккомкачедтеароффобжект:: ~ Ккомкачедтеароффобжект](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомкачедтеароффобжект:: AddRef](#addref)|Увеличивает значение счетчика ссылок для `CComCachedTearOffObject` объекта.|
|[Ккомкачедтеароффобжект:: Финалконструкт](#finalconstruct)|Вызывает метод `m_contained::FinalConstruct` (метода удаления класса).|
|[Ккомкачедтеароффобжект:: Финалрелеасе](#finalrelease)|Вызывает метод `m_contained::FinalRelease` (метода удаления класса).|
|[Ккомкачедтеароффобжект:: QueryInterface](#queryinterface)|Возвращает указатель на `IUnknown` `CComCachedTearOffObject` объект или на запрошенный интерфейс в классе отрыва (класс `contained`).|
|[Ккомкачедтеароффобжект:: Release](#release)|Уменьшает значение счетчика ссылок для `CComCachedTearOffObject` объекта и уничтожает его, если счетчик ссылок равен 0.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Ккомкачедтеароффобжект:: m_contained](#m_contained)|Объект, производный от класса отрыва (класса `contained`). `CComContainedObject`|

## <a name="remarks"></a>Примечания

`CComCachedTearOffObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для интерфейса разрыва. Этот класс отличается от `CComTearOffObject` класса в `CComCachedTearOffObject` , который имеет `IUnknown`свой собственный, отделенный от объекта `IUnknown` -владельца (владелец — это объект, для которого создается уничтожение). `CComCachedTearOffObject`сохраняет собственный счетчик ссылок на его `IUnknown` и удаляет себя, когда счетчик ссылок равен нулю. Однако при запросе любого из своих интерфейсов разрыва счетчик ссылок объекта `IUnknown` Owner будет увеличен.

Если экземпляр, реализующий уничтожение, уже создан, а интерфейс разрыва запрашивается снова, то тот же `CComCachedTearOffObject` объект используется повторно. `CComCachedTearOffObject` Напротив, если интерфейс разрыва, реализованный `CComTearOffObject` с помощью, снова запрашивается через объект Owner, будет создан экземпляр другого. `CComTearOffObject`

Класс `FinalRelease` owner должен реализовывать и вызывать `Release` `IUnknown` в кэше для, что приводит к уменьшению счетчика ссылок. `CComCachedTearOffObject` Это приведет `CComCachedTearOffObject` `FinalRelease` к вызову и удалению разрыва.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="addref"></a>Ккомкачедтеароффобжект:: AddRef

Увеличивает значение счетчика `CComCachedTearOffObject` ссылок объекта на 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики и тестирования.

##  <a name="ccomcachedtearoffobject"></a>Ккомкачедтеароффобжект:: Ккомкачедтеароффобжект

Конструктор.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
окне Указатель на объект `IUnknown`. `CComCachedTearOffObject`

### <a name="remarks"></a>Примечания

Инициализирует `CComContainedObject` член [m_contained](#m_contained).

##  <a name="dtor"></a>Ккомкачедтеароффобжект:: ~ Ккомкачедтеароффобжект

Деструктор

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызывает [финалрелеасе](#finalrelease).

##  <a name="finalconstruct"></a>Ккомкачедтеароффобжект:: Финалконструкт

Вызывает `m_contained::FinalConstruct` метод Create `m_contained` `CComContainedObject`, >объект,`contained`используемый для доступа к интерфейсу, реализованному классом отрыва. < 

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="finalrelease"></a>Ккомкачедтеароффобжект:: Финалрелеасе

Вызовы `m_contained::FinalRelease` для освобождения `m_contained`, `CComContainedObject` объект>`contained`. < 

```
void FinalRelease();
```

##  <a name="m_contained"></a>Ккомкачедтеароффобжект:: m_contained

Объект [ккомконтаинедобжект](../../atl/reference/ccomcontainedobject-class.md) , производный от класса отрыва.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>Параметры

*нем*<br/>
окне Класс отрыва, производный от `CComTearOffObjectBase` , и интерфейсы, которые должен поддерживать ваш объект отрыва.

### <a name="remarks"></a>Примечания

Методы `m_contained` , наследуемые, используются для доступа к интерфейсу разрыва в классе отрыва через кэшированный `QueryInterface`объект разрыва, `FinalConstruct`и `FinalRelease`.

##  <a name="queryinterface"></a>Ккомкачедтеароффобжект:: QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по *IID*, или значение null, если интерфейс не найден.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Если запрошенный интерфейс имеет `IUnknown`значение, функция возвращает указатель `CComCachedTearOffObject`на себя `IUnknown` и увеличивает счетчик ссылок. В противном случае запрашивает интерфейс в классе отрыва с помощью метода [интерналкуеринтерфаце](ccomobjectrootex-class.md#internalqueryinterface) , унаследованного `CComObjectRootEx`от.

##  <a name="release"></a>Ккомкачедтеароффобжект:: Release

Уменьшает значение счетчика ссылок на 1 и, если счетчик ссылок равен 0, удаляет `CComCachedTearOffObject` объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В сборках, не относящихся к отладке, всегда возвращает 0. В отладочных сборках возвращает значение, которое может быть полезно для диагностики или тестирования.

## <a name="see-also"></a>См. также

[Класс CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
