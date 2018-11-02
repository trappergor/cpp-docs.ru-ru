---
title: Класс CComClassFactory
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 61dd67a4a34be447807799537971c19c11d09e5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575231"
---
# <a name="ccomclassfactory-class"></a>Класс CComClassFactory

Этот класс реализует [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) интерфейс.

## <a name="syntax"></a>Синтаксис

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComClassFactory::CreateInstance](#createinstance)|Создает объект для указанного идентификатора CLSID.|
|[CComClassFactory::LockServer](#lockserver)|Блокирует фабрики класса в памяти.|

## <a name="remarks"></a>Примечания

`CComClassFactory` реализует [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) интерфейс, который содержит методы для создания объекта определенного CLSID, а также для блокировки фабрики классов в памяти, позволяющие быстрее создавать новые объекты. `IClassFactory` должен быть реализован для каждого класса, который зарегистрирован в системном реестре и в которой назначения CLSID.

Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет `CComClassFactory` как фабрики класса по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите один из `DECLARE_CLASSFACTORY` *XXX* макросы в определении класса. Например [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) макрос использует указанный класс фабрики класса:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

Указывает, что выше определения класса `CMyClassFactory` будет использоваться в качестве фабрики класса по умолчанию для объекта. `CMyClassFactory` должен быть производным от `CComClassFactory` и Переопределите `CreateInstance`.

Библиотека ATL предоставляет три другие макросы, которые объявляют фабрику класса:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который отвечающей за создание через лицензию.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), которая создает один [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объекта.

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory::CreateInstance

Создает объект для указанного идентификатора CLSID и получает указатель интерфейса на этот объект.

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

##  <a name="lockserver"></a>  CComClassFactory::LockServer

Увеличивает и уменьшает счетчик блокировки модуля путем вызова `_Module::Lock` и `_Module::Unlock`, соответственно.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*fLock*<br/>
[in] Если значение равно TRUE, увеличивается счетчик блокировок; в противном случае уменьшается количество блокировок.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`_Module` ссылается на глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.

Вызов `LockServer` позволяет клиенту, чтоб фабрику класса для создания нескольких объектов можно быстро.

## <a name="see-also"></a>См. также

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
