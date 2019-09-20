---
title: Класс CComAggObject
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: 8b05284104f9d2e5e7704bceaee6f8adf9a33aac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497659"
---
# <a name="ccomaggobject-class"></a>Класс CComAggObject

Этот класс реализует интерфейс [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для агрегированного объекта. По определению агрегированный объект содержится внутри внешнего объекта. Класс аналогичен [классу CComObject](../../atl/reference/ccomobject-class.md), за исключением того, что он предоставляет интерфейс, напрямую доступный внешним клиентам. `CComAggObject`

## <a name="syntax"></a>Синтаксис

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Параметры

*нем*<br/>
Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которые требуется поддерживать для объекта.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComAggObject:: CComAggObject](#ccomaggobject)|Конструктор.|
|[CComAggObject:: ~ CComAggObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComAggObject:: AddRef](#addref)|Увеличивает значение счетчика ссылок для агрегированного объекта.|
|[CComAggObject:: CreateInstance](#createinstance)|Эта статическая функция позволяет создать новый объект **<** `contained` **>** CComAggObject без дополнительной нагрузки на [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComAggObject:: Финалконструкт](#finalconstruct)|Выполняет окончательную инициализацию `m_contained`.|
|[CComAggObject:: Финалрелеасе](#finalrelease)|Выполняет окончательное уничтожение `m_contained`.|
|[CComAggObject:: QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComAggObject:: Release](#release)|Уменьшает значение счетчика ссылок на агрегированный объект.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CComAggObject:: m_contained](#m_contained)|Делегирует `IUnknown` вызовы внешней неизвестной.|

## <a name="remarks"></a>Примечания

`CComAggObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для агрегированного объекта. `CComAggObject`имеет собственный `IUnknown` интерфейс, отделенный от `IUnknown` интерфейса внешнего объекта и сохраняющий собственный счетчик ссылок.

Дополнительные сведения о статистической обработке см. в статье [основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="addref"></a>CComAggObject:: AddRef

Увеличивает значение счетчика ссылок для агрегированного объекта.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

##  <a name="ccomaggobject"></a>CComAggObject:: CComAggObject

Конструктор.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
окне Внешняя неизвестная.

### <a name="remarks"></a>Примечания

Инициализирует элемент `CComContainedObject` [m_contained](#m_contained) и увеличивает счетчик блокировок модуля.

Деструктор уменьшает счетчик блокировок модуля.

##  <a name="dtor"></a>CComAggObject:: ~ CComAggObject

Деструктор

```
~CComAggObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызывает [финалрелеасе](#finalrelease)и уменьшает число блокировок модуля.

##  <a name="createinstance"></a>CComAggObject:: CreateInstance

Эта статическая функция позволяет создать новый объект **<** `contained` **>** CComAggObject без дополнительной нагрузки на [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Параметры

*PP*<br/>
заполняет Указатель на **CComAggObject\<** ,<em>содержащий</em> **>** указатель. Если `CreateInstance` операция завершилась неудачно, *PP* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Возвращаемый объект имеет нулевое значение счетчика ссылок, поэтому `AddRef` вызовите его немедленно `Release` , а затем используйте для освобождения ссылки на указатель объекта по завершении.

Если прямой доступ к объекту не требуется, но по-прежнему требуется создать новый объект без дополнительной нагрузки `CoCreateInstance`, используйте [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) .

##  <a name="finalconstruct"></a>CComAggObject:: Финалконструкт

Метод, вызываемый на последних стадиях создания объекта, выполняет последнюю инициализацию элемента [m_contained](#m_contained) .

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="finalrelease"></a>CComAggObject:: Финалрелеасе

Этот метод вызывается при уничтожении объекта, освобождая член [m_contained](#m_contained) .

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComAggObject:: m_contained

Объект [ккомконтаинедобжект](../../atl/reference/ccomcontainedobject-class.md) , производный от класса.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Параметры

*нем*<br/>
окне Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которые требуется поддерживать для объекта.

### <a name="remarks"></a>Примечания

Все `IUnknown` вызовы через `m_contained` делегируются внешней неизвестной.

##  <a name="queryinterface"></a>CComAggObject:: QueryInterface

Извлекает указатель на запрошенный интерфейс.

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

### <a name="remarks"></a>Примечания

Если запрошенный интерфейс имеет `IUnknown`значение `QueryInterface` , `IUnknown` функция возвращает указатель на агрегатный объект и увеличивает счетчик ссылок. В противном случае этот метод запрашивает интерфейс через `CComContainedObject` член [m_contained](#m_contained).

##  <a name="release"></a>CComAggObject:: Release

Уменьшает значение счетчика ссылок на агрегированный объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В сборках, не относящихся к отладке, `Release` всегда возвращает 0.

## <a name="see-also"></a>См. также

[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
