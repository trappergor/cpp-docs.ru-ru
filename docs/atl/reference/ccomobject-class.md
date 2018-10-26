---
title: Класс CComObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fdd5bcf0bf3ac58cf056543b9dbe3c55b6fe1bd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073245"
---
# <a name="ccomobject-class"></a>Класс CComObject

Этот класс реализует `IUnknown` неагрегированные объекта.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>Параметры

*Base*<br/>
Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которую требуется поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComObject::CComObject](#ccomobject)|Конструктор.|
|[CComObject::~CComObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComObject::AddRef](#addref)|Увеличивает счетчик ссылок на объект.|
|[CComObject::CreateInstance](#createinstance)|(Статический) Создает новый `CComObject` объекта.|
|[CComObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComObject::Release](#release)|Уменьшает счетчик ссылок на объект.|

## <a name="remarks"></a>Примечания

`CComObject` реализует [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) неагрегированные объекта. Тем не менее, вызовы `QueryInterface`, `AddRef`, и `Release` делегируются `CComObjectRootEx`.

Дополнительные сведения об использовании `CComObject`, см. в статье [основы объекта ATL COM-объекты](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="addref"></a>  CComObject::AddRef

Увеличивает счетчик ссылок на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает новый счетчик ссылок увеличивается в объекте. Это значение может быть полезно для диагностики или тестирования.

##  <a name="ccomobject"></a>  CComObject::CComObject

Конструктор увеличивает счетчик блокировки модуля.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Параметры

<em>void\*</em><br/>
[in] Этот параметр без имени не используется. Он существует для согласованности с другими `CComXXXObjectXXX` конструкторы.

### <a name="remarks"></a>Примечания

Деструктор уменьшает его.

Если `CComObject`-производный объект успешно создается с помощью **новый** оператор, начальное значение счетчика ссылок равно 0. Устанавливает значение счетчика ссылок на соответствующее значение (1), чтобы вызов [AddRef](#addref) функции.

##  <a name="dtor"></a>  CComObject::~CComObject

Деструктор

```
CComObject();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, вызовы [FinalRelease](ccomobjectrootex-class.md#finalrelease), и уменьшает счетчик блокировки модуля.

##  <a name="createinstance"></a>  CComObject::CreateInstance

Эта статическая функция позволяет создать новую **CComObject <** `Base` **>** объекта без использования [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Параметры

*PP*<br/>
[out] Указатель на **CComObject <** `Base` **>** указатель. Если `CreateInstance` завершилась неудачно, *pp* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Возвращаемый объект имеет нулевое число ссылок, назовем `AddRef` немедленно, используйте `Release` освободить ссылку на указатель на объект, когда все будет готово.

Если вы не нужен прямой доступ к объекту, но по-прежнему хотите создать новый объект без необходимости проведения `CoCreateInstance`, использовать [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо этого.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

##  <a name="queryinterface"></a>  CComObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

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

##  <a name="release"></a>  CComObject::Release

Уменьшает счетчик ссылок на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает новый счетчик ссылок уменьшается на единицу в объекте. В отладочных сборках возвращаемое значение может быть полезно для диагностики или тестирования. В неотладочных сборках `Release` всегда возвращает значение 0.

## <a name="see-also"></a>См. также

[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
