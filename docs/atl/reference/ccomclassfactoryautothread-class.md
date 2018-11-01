---
title: Класс CComClassFactoryAutoThread
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: 30a9d52ff661fd4fa39344382402aa6ff09d193f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574828"
---
# <a name="ccomclassfactoryautothread-class"></a>Класс CComClassFactoryAutoThread

Этот класс реализует [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) интерфейс и позволяет создавать в нескольких подразделениях объекты.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Создает объект для указанного идентификатора CLSID.|
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Блокирует фабрики класса в памяти.|

## <a name="remarks"></a>Примечания

`CComClassFactoryAutoThread` аналогичен [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет создавать в нескольких подразделениях объекты. Чтобы воспользоваться преимуществами этой поддержки, являются производными модуле exe-файла из [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрики класса по умолчанию. Чтобы использовать `CComClassFactoryAutoThread`, укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) макроса в определении класса объекта. Пример:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactoryAutoThread::CreateInstance

Создает объект для указанного идентификатора CLSID и получает указатель интерфейса на этот объект.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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

### <a name="remarks"></a>Примечания

Если модуль является производным от [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` сначала выбирает поток для создания объекта в связанного подразделения.

##  <a name="lockserver"></a>  CComClassFactoryAutoThread::LockServer

Увеличивает и уменьшает счетчик блокировки модуля путем вызова `_Module::Lock` и `_Module::Unlock`, соответственно.

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*fLock*<br/>
[in] Если значение равно TRUE, увеличивается счетчик блокировок; в противном случае уменьшается количество блокировок.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

При использовании `CComClassFactoryAutoThread`, `_Module` обычно относится к глобальному экземпляру [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).

Вызов `LockServer` позволяет клиенту, чтоб фабрику класса для создания нескольких объектов можно быстро.

## <a name="see-also"></a>См. также

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[Класс CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)<br/>
[Класс CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
