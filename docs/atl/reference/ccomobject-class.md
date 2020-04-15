---
title: Класс CComObject
ms.date: 11/04/2016
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
ms.openlocfilehash: de6ffb45fe5c6f73ab656d5c6185b70d9f5edd38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327642"
---
# <a name="ccomobject-class"></a>Класс CComObject

Этот класс `IUnknown` реализуется для неагрегированного объекта.

## <a name="syntax"></a>Синтаксис

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Ваш класс, полученный из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx,](../../atl/reference/ccomobjectrootex-class.md)а также из любых других интерфейсов, которые вы хотите поддерживать на объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComObject::CComObject](#ccomobject)|Конструктор.|
|[CComObject:::CComObject](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComObject:AddRef](#addref)|Приращения, отсылки рассчитывают на объект.|
|[CComObject::СозданиеInstance](#createinstance)|(Статик) Создает новый `CComObject` объект.|
|[CComObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComObject::Release](#release)|Декретирует значение ссылки на объект.|

## <a name="remarks"></a>Remarks

`CComObject`реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) для неагрегированного объекта. Тем не `QueryInterface`менее, `AddRef` `Release` звонки, и `CComObjectRootEx`делегируются .

Для получения дополнительной `CComObject`информации об использовании , см. [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObject`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomobjectaddref"></a><a name="addref"></a>CComObject:AddRef

Приращения, отсылки рассчитывают на объект.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает новый приращенный отсчет ссылки на объект. Это значение может быть полезно для диагностики или тестирования.

## <a name="ccomobjectccomobject"></a><a name="ccomobject"></a>CComObject::CComObject

Конструктор приращает количество блокировки модуля.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>Параметры

<em>void\*</em><br/>
(в) Этот неназванный параметр не используется. Она существует для симметрии с другими `CComXXXObjectXXX` конструкторами.

### <a name="remarks"></a>Remarks

Деструктор пристыковывает его.

Если `CComObject`объект, полученный из полученных, успешно построен с помощью **нового** оператора, начальный отсчет ссылок составляет 0. Чтобы установить значение ссылки на правильное значение (1), позвоните в функцию [AddRef.](#addref)

## <a name="ccomobjectccomobject"></a><a name="dtor"></a>CComObject:::CComObject

Деструктор

```
CComObject();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы, вызывает [FinalRelease](ccomobjectrootex-class.md#finalrelease)и высчитывает количество блокировки модуля.

## <a name="ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject::СозданиеInstance

Эта статическая функция позволяет создавать новый **объект CComObject<,** `Base` **>** без накладных расходов [CoCreateInstance.](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>Параметры

*Pp*<br/>
(ваут) Указатель на **указатель CComObject<.** `Base` **>** Если `CreateInstance` неудача, *pp* установлен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Возвращается объект имеет подсчет ссылок `AddRef` ноль, `Release` поэтому немедленно позвоните, а затем используйте для освобождения ссылки на указатель объекта, когда вы закончите.

Если вам не нужен прямой доступ к объекту, но все `CoCreateInstance`же хотите создать новый объект без накладных расходов, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо этого.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

## <a name="ccomobjectqueryinterface"></a><a name="queryinterface"></a>CComObject::QueryInterface

Извлекает указатель на запрошенный интерфейс.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) Идентификатор запрашиваемого интерфейса.

*ppvObject*<br/>
(ваут) Указатель на указатель интерфейса, идентифицированный *iid.* Если объект не поддерживает этот интерфейс, *ppvObject* настроен на NULL.

*Pp*<br/>
(ваут) Указатель на указатель интерфейса, `Q`идентифицированный по типу. Если объект не поддерживает этот интерфейс, *pp* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomobjectrelease"></a><a name="release"></a>CComObject::Release

Декретирует значение ссылки на объект.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция возвращает новый decremented отсчет ссылки на объект. В сборках отладок значение возврата может быть полезно для диагностики или тестирования. В неотлибуговых `Release` сборках всегда возвращается 0.

## <a name="see-also"></a>См. также раздел

[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
