---
title: Класс CComPolyObject
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
ms.openlocfilehash: deed29b5fb80ea8bbd06b3d50f45e38740b1619f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497154"
---
# <a name="ccompolyobject-class"></a>Класс CComPolyObject

Этот класс реализует `IUnknown` для агрегированного или неагрегированного объекта.

## <a name="syntax"></a>Синтаксис

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Параметры

*нем*<br/>
Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которые требуется поддерживать для объекта.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CComPolyObject:: CComPolyObject](#ccompolyobject)|Конструктор.|
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CComPolyObject:: AddRef](#addref)|Увеличивает значение счетчика ссылок объекта.|
|[CComPolyObject:: CreateInstance](#createinstance)|Статически Позволяет создать новый объект **<** `contained` **>** CComPolyObject без дополнительной нагрузки на [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComPolyObject:: Финалконструкт](#finalconstruct)|Выполняет окончательную инициализацию `m_contained`.|
|[CComPolyObject:: Финалрелеасе](#finalrelease)|Выполняет окончательное уничтожение `m_contained`.|
|[CComPolyObject:: QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComPolyObject:: Release](#release)|Уменьшает значение счетчика ссылок объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CComPolyObject:: m_contained](#m_contained)|Делегирует `IUnknown` вызовы внешнему неизвестному объекту, если объект является агрегатным `IUnknown` , или с объектом, если объект не является агрегированным.|

## <a name="remarks"></a>Примечания

`CComPolyObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для агрегированного или неагрегированного объекта.

При создании экземпляра `CComPolyObject` проверяется значение внешней неизвестной. Если он равен null, `IUnknown` реализуется для неагрегированного объекта. Если внешнее неизвестное значение не `IUnknown` равно null, реализуется для агрегированного объекта.

Преимущество использования заключается в `CComPolyObject` том, что не следует одновременно использовать [CComAggObject](../../atl/reference/ccomaggobject-class.md) и [CComObject](../../atl/reference/ccomobject-class.md) в модуле для обработки агрегированных и неагрегированных вариантов. В обоих `CComPolyObject` случаях обрабатывается один объект. Это означает, что в модуле существует только одна копия таблицы vtable и одна копия функций. Если таблица vtable велика, это может значительно снизить размер модуля. Однако если таблица vtable невелика, использование `CComPolyObject` может привести к тому, что размер модуля будет немного больше, поскольку он не оптимизирован для агрегированного или неагрегированного объекта, `CComAggObject` как `CComObject`и.

Если макрос DECLARE_POLY_AGGREGATABLE указан в определении класса объекта, `CComPolyObject` будет использоваться для создания объекта. DECLARE_POLY_AGGREGATABLE будет автоматически объявлен при использовании мастера проектов ATL для создания элемента управления "полный доступ" или "Internet Explorer".

При статистическом вычислении `CComPolyObject` объект имеет собственный `IUnknown`, отдельный `IUnknown`от внешнего объекта и сохраняет свой собственный счетчик ссылок. `CComPolyObject`использует [ккомконтаинедобжект](../../atl/reference/ccomcontainedobject-class.md) для делегирования внешней неизвестной.

Дополнительные сведения о статистической обработке см. в статье [основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="addref"></a>CComPolyObject:: AddRef

Увеличивает значение счетчика ссылок на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

##  <a name="ccompolyobject"></a>CComPolyObject:: CComPolyObject

Конструктор.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
окне Указатель на внешнюю неизвестную функцию, если объект должен быть агрегирован, или значение NULL, если объект не является агрегированным.

### <a name="remarks"></a>Примечания

Инициализирует `CComContainedObject` [элемент данных](#m_contained),m_containedиувеличиваетсчетчикблокировок модуля.

Деструктор уменьшает счетчик блокировок модуля.

##  <a name="dtor"></a>CComPolyObject:: ~ CComPolyObject

Деструктор

```
~CComPolyObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызывает [финалрелеасе](#finalrelease)и уменьшает число блокировок модуля.

##  <a name="createinstance"></a>CComPolyObject:: CreateInstance

Позволяет создать новый объект **<** `contained` **>** CComPolyObject без дополнительной нагрузки на [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Параметры

*PP*<br/>
заполняет Указатель на указатель **<** `contained` **>** CComPolyObject. Если `CreateInstance` операция завершилась неудачно, *PP* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Возвращаемый объект имеет нулевое значение счетчика ссылок, поэтому `AddRef` вызовите его немедленно `Release` , а затем используйте для освобождения ссылки на указатель объекта по завершении.

Если прямой доступ к объекту не требуется, но по-прежнему требуется создать новый объект без дополнительной нагрузки `CoCreateInstance`, используйте [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) .

##  <a name="finalconstruct"></a>CComPolyObject:: Финалконструкт

Метод, вызываемый на последних стадиях создания объекта, выполняет последнюю инициализацию элемента данных [m_contained](#m_contained) .

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="finalrelease"></a>CComPolyObject:: Финалрелеасе

Этот метод вызывается при уничтожении объекта, освобождая элемент данных [m_contained](#m_contained) .

```
void FinalRelease();
```

##  <a name="m_contained"></a>CComPolyObject:: m_contained

Объект [ккомконтаинедобжект](../../atl/reference/ccomcontainedobject-class.md) , производный от класса.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Параметры

*нем*<br/>
окне Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которые требуется поддерживать для объекта.

### <a name="remarks"></a>Примечания

`IUnknown`вызовы через `m_contained` вызываются внешней неизвестностью, если объект является агрегатным, или `IUnknown` с объектом этого объекта, если объект не является агрегированным.

##  <a name="queryinterface"></a>CComPolyObject:: QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*Q*<br/>
COM-интерфейс.

*IID*<br/>
окне Идентификатор запрашиваемого интерфейса.

*ппвобжект*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый по *IID*. Если объект не поддерживает этот интерфейс, *ппвобжект* имеет значение null.

*PP*<br/>
заполняет Указатель на интерфейс, заданный параметром `__uuidof(Q)`.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Для агрегированного объекта, если запрошенный интерфейс имеет `IUnknown`значение, `QueryInterface` функция возвращает указатель на `IUnknown` агрегатный объект и увеличивает счетчик ссылок. В противном случае этот метод запрашивает интерфейс через `CComContainedObject` элемент данных [m_contained](#m_contained).

##  <a name="release"></a>CComPolyObject:: Release

Уменьшает значение счетчика ссылок на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В неотладочных сборках `Release` всегда возвращает 0.

## <a name="see-also"></a>См. также

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
