---
title: Класс CComPolyObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78e45db5cf68c4a92fc9e8165ed648760d02e8fb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069455"
---
# <a name="ccompolyobject-class"></a>Класс CComPolyObject

Этот класс реализует `IUnknown` для суммирования или неагрегированные объекта.

## <a name="syntax"></a>Синтаксис

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Параметры

*содержится*<br/>
Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которую требуется поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Конструктор.|
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComPolyObject::AddRef](#addref)|Увеличивает счетчик ссылок объекта.|
|[CComPolyObject::CreateInstance](#createinstance)|(Статический) Позволяет создать новую **CComPolyObject <** `contained` **>** объекта без использования [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).|
|[CComPolyObject::FinalConstruct](#finalconstruct)|Выполняет окончательной инициализации `m_contained`.|
|[CComPolyObject::FinalRelease](#finalrelease)|Выполняет окончательный деструкция `m_contained`.|
|[CComPolyObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComPolyObject::Release](#release)|Уменьшает счетчик ссылок объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|Делегаты `IUnknown` вызывает внешняя Неизвестная строка, если объект является статистическим или `IUnknown` объекта, если объект не является агрегатом.|

## <a name="remarks"></a>Примечания

`CComPolyObject` реализует [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) для суммирования или неагрегированные объекта.

При создании экземпляра класса `CComPolyObject` создается значение внешнего проверяется unknown. Если он равен NULL, `IUnknown` реализуется для объекта неагрегированные. Если внешняя Неизвестная строка не равно NULL, `IUnknown` реализуется для объединенного объекта.

Преимущество использования `CComPolyObject` — избежать обеих [CComAggObject](../../atl/reference/ccomaggobject-class.md) и [CComObject](../../atl/reference/ccomobject-class.md) в модуле для обработки вариантов, статистические и неагрегированные. Один `CComPolyObject` объект обрабатывает в обоих случаях. Это означает, что только одна копия таблицы vtable и одна копия функции существуют в модуле. Если в таблице vtable имеет большой размер, это может значительно снизить размер вашего модуля. Тем не менее, если в таблице vtable невелик, с помощью `CComPolyObject` может привести к немного больший размер модуля, поскольку метод не оптимизирован для суммирования или неагрегированные объекта, так как `CComAggObject` и `CComObject`.

Если макрос DECLARE_POLY_AGGREGATABLE, указанный в определении класса объекта, `CComPolyObject` будет использоваться для создания объекта. DECLARE_POLY_AGGREGATABLE будет объявлено автоматически в том случае, если вы используете мастер проектов ATL для создания полного доступа или управления Internet Explorer.

Если статистическая обработка, `CComPolyObject` объект имеет свой собственный `IUnknown`, отдельно от внешнего объекта `IUnknown`и ведет собственный счетчик ссылок. `CComPolyObject` использует [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) делегировать внешняя Неизвестная строка.

Дополнительные сведения о статистической обработке см. в статье [основы объекта ATL COM-объекты](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="addref"></a>  CComPolyObject::AddRef

Увеличивает счетчик ссылок на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, которое может быть полезно для диагностики или тестирования.

##  <a name="ccompolyobject"></a>  CComPolyObject::CComPolyObject

Конструктор.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
[in] Указатель на внешний unknown, если объект должен выполнить статистическую обработку, или значение NULL, если объект, если объект не является агрегатом.

### <a name="remarks"></a>Примечания

Инициализирует `CComContainedObject` данные-член, [m_contained](#m_contained)и увеличивает счетчик блокировки модуля.

Деструктор уменьшает счетчик блокировки модуля.

##  <a name="dtor"></a>  CComPolyObject:: ~ CComPolyObject

Деструктор

```
~CComPolyObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызовы [FinalRelease](#finalrelease), и уменьшает счетчик блокировки модуля.

##  <a name="createinstance"></a>  CComPolyObject::CreateInstance

Позволяет создать новую **CComPolyObject <** `contained` **>** объекта без использования [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>Параметры

*PP*<br/>
[out] Указатель на **CComPolyObject <** `contained` **>** указатель. Если `CreateInstance` завершилась неудачно, *pp* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Возвращаемый объект имеет нулевое число ссылок, назовем `AddRef` немедленно, используйте `Release` освободить ссылку на указатель на объект, когда все будет готово.

Если вы не требующие прямого доступа к объекту, но по-прежнему хотите создать новый объект без необходимости проведения `CoCreateInstance`, использовать [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо этого.

##  <a name="finalconstruct"></a>  CComPolyObject::FinalConstruct

Вызывается во время последних этапов создания объекта, этот метод выполняет инициализацию окончательный [m_contained](#m_contained) данные-член.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="finalrelease"></a>  CComPolyObject::FinalRelease

Вызывается во время уничтожения объекта, этот метод освобождает [m_contained](#m_contained) данные-член.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComPolyObject::m_contained

Объект [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) объект, производный от этого класса.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Параметры

*содержится*<br/>
[in] Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которую требуется поддерживать на объекте.

### <a name="remarks"></a>Примечания

`IUnknown` выполняет вызов через `m_contained` делегируются внешняя Неизвестная строка, если объект является статистическим, или `IUnknown` этого объекта, если объект не является агрегатом.

##  <a name="queryinterface"></a>  CComPolyObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*Q*<br/>
COM-интерфейса.

*IID*<br/>
[in] Идентификатор запрашиваемого интерфейса.

*ppvObject*<br/>
[out] Указатель на указатель интерфейса, идентифицируемый *iid*. Если объект не поддерживает этот интерфейс *ppvObject* имеет значение NULL.

*PP*<br/>
[out] Указатель на интерфейс, определенный `__uuidof(Q)`.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Для вычисляемого объекта, если запрошенный интерфейс `IUnknown`, `QueryInterface` возвращает указатель на объединенные объекта собственные `IUnknown` и увеличивает счетчик ссылок. В противном случае этот метод отправляет запрос для интерфейса через `CComContainedObject` данные-член, [m_contained](#m_contained).

##  <a name="release"></a>  CComPolyObject::Release

Уменьшает счетчик ссылок на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В сборках отладки `Release` всегда возвращает значение 0.

## <a name="see-also"></a>См. также

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
