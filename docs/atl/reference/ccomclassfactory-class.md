---
title: Класс Ккомклассфактори
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 892153e47ac4e9dd45d5dfc01b76f1ce29d23938
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497454"
---
# <a name="ccomclassfactory-class"></a>Класс Ккомклассфактори

Этот класс реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) .

## <a name="syntax"></a>Синтаксис

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомклассфактори:: CreateInstance](#createinstance)|Создает объект указанного идентификатора CLSID.|
|[Ккомклассфактори:: Локксервер](#lockserver)|Блокирует фабрику класса в памяти.|

## <a name="remarks"></a>Примечания

`CComClassFactory`реализует интерфейс [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory) , который содержит методы для создания объекта определенного идентификатора CLSID, а также блокирует фабрику класса в памяти, чтобы новые объекты могли создаваться быстрее. `IClassFactory`должен быть реализован для каждого класса, регистрируемого в системном реестре и которому назначается идентификатор CLSID.

Объекты ATL обычно получают фабрику классов путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет `CComClassFactory` фабрику классов по умолчанию. Чтобы переопределить это значение по умолчанию, укажите `DECLARE_CLASSFACTORY`один из макросов *xxx* в определении класса. Например, макрос [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) использует указанный класс для фабрики класса:

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

Приведенное выше определение класса указывает `CMyClassFactory` , что будет использоваться в качестве фабрики класса по умолчанию для объекта. `CMyClassFactory`должен быть производным `CComClassFactory` от и `CreateInstance`переопределять.

ATL предоставляет три других макроса, которые объявляют фабрику класса:

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который управляет созданием с помощью лицензии.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Использует [ккомклассфакторяутосреад](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) Использует [ккомклассфакторисинглетон](../../atl/reference/ccomclassfactorysingleton-class.md), который конструирует один объект [ккомобжектглобал](../../atl/reference/ccomobjectglobal-class.md) .

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="createinstance"></a>Ккомклассфактори:: CreateInstance

Создает объект указанного идентификатора CLSID и получает указатель интерфейса на этот объект.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Параметры

*пункаутер*<br/>
окне Если объект создается как часть агрегата, *пункаутер* должен быть внешним неизвестным. В противном случае *пункаутер* должен иметь значение null.

*riid*<br/>
окне IID запрашиваемого интерфейса. Если *пункаутер* не равен null, *riid* должен иметь `IID_IUnknown`значение.

*ппвобж*<br/>
заполняет Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс, *ппвобж* имеет значение null.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

##  <a name="lockserver"></a>Ккомклассфактори:: Локксервер

Увеличивает и уменьшает счетчик блокировок модуля, вызывая `_Module::Lock` и `_Module::Unlock`соответственно.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*флокк*<br/>
окне Если значение равно TRUE, счетчик блокировок увеличивается; в противном случае счетчик блокировок уменьшается.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

`_Module`ссылается на глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или производный от него класс.

Вызов `LockServer` позволяет клиенту хранить фабрику класса, чтобы можно было быстро создавать несколько объектов.

## <a name="see-also"></a>См. также

[Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[ккомглобалссреадмодел](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
