---
title: Класс CComClassFactorySingleton
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: 480b4c2a6e052e8e0823b97b548fc5d07b55230f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290395"
---
# <a name="ccomclassfactorysingleton-class"></a>Класс CComClassFactorySingleton

Этот класс является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс.

`CComClassFactorySingleton` является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта. Каждый вызов `CreateInstance` метод просто запрашивает этот объект для указателя на интерфейс.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Запросы `m_spObj` для указателя на интерфейс.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объект, созданный с `CComClassFactorySingleton`.|

## <a name="remarks"></a>Примечания

Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет `CComClassFactory` как фабрики класса по умолчанию. Чтобы использовать `CComClassFactorySingleton`, укажите [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) макроса в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance

Вызовы `QueryInterface` через [m_spObj](#m_spobj) для получения указателя на интерфейс.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Параметры

*pUnkOuter*<br/>
[in] Если объект создается как часть агрегата, затем *pUnkOuter* должен быть внешняя Неизвестная строка. В противном случае *pUnkOuter* должен иметь значение NULL.

*riid*<br/>
[in] Идентификатор IID запрошенного интерфейса. Если *pUnkOuter* отлично от NULL, *riid* должно быть `IID_IUnknown`.

*ppvObj*<br/>
[out] Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppvObj* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj

[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объект, созданный с `CComClassFactorySingleton`.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>Примечания

Каждый вызов [CreateInstance](#createinstance) метод просто запрашивает этот объект для указателя на интерфейс.

Обратите внимание, что текущий способ `m_spObj` представляет критическое изменение из-за способа, `CComClassFactorySingleton` работали в предыдущих версиях библиотеки ATL. В предыдущих версиях `CComClassFactorySingleton` объект был создан в то же время, так как фабрика класса, при инициализации сервера. В Visual C++ .NET 2003 создается объект неактивно, при первом запросе. Это изменение может привести к ошибкам в программ, использующих ранних инициализации.

## <a name="see-also"></a>См. также

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[Класс CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)<br/>
[Класс CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
