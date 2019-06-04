---
title: Класс IPersistPropertyBagImpl
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: 569a24fd08801de952e998f772afbc3478096628
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503149"
---
# <a name="ipersistpropertybagimpl-class"></a>Класс IPersistPropertyBagImpl

Этот класс реализует `IUnknown` и позволяет сохранить его свойства в контейнер свойств, предоставляемых клиентом объекту.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IPersistPropertyBagImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Извлекает идентификатор CLSID объекта.|
|[IPersistPropertyBagImpl::InitNew](#initnew)|Инициализирует только что созданный объект. Реализация ATL, возвращается значение s_ок.|
|[IPersistPropertyBagImpl::Load](#load)|Загружает свойства объекта из контейнера свойств, предоставляемых клиентом.|
|[IPersistPropertyBagImpl::Save](#save)|Сохраняет свойства объекта в контейнер свойств, предоставляемых клиентом.|

## <a name="remarks"></a>Примечания

[IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) интерфейс позволяет объекту сохранить свои свойства в контейнер свойств, предоставляемых клиентом. Класс `IPersistPropertyBagImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

`IPersistPropertyBag` работает в сочетании с [IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) и [IErrorLog](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\)). Эти последний два интерфейса должен быть реализован с помощью клиента. Через `IPropertyBag`, клиент сохраняет и загружает отдельных свойств объекта. Через `IErrorLog`, объект и на клиенте можно сообщить о каких-либо ошибок.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID

Извлекает идентификатор CLSID объекта.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) в Windows SDK.

##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew

Инициализирует только что созданный объект.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. в разделе [IPersistPropertyBag::InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) в Windows SDK.

##  <a name="load"></a>  IPersistPropertyBagImpl::Load

Загружает свойства объекта из контейнера свойств, предоставляемых клиентом.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Примечания

ATL использует сопоставление свойств объекта для извлечения этой информации.

См. в разделе [IPersistPropertyBag::Load](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) в Windows SDK.

##  <a name="save"></a>  IPersistPropertyBagImpl::Save

Сохраняет свойства объекта в контейнер свойств, предоставляемых клиентом.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Примечания

ATL использует сопоставление свойств объекта для хранения подобной информации. По умолчанию этот метод сохраняет все свойства, независимо от значения *fSaveAllProperties*.

См. в разделе [IPersistPropertyBag::Save](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) в Windows SDK.

## <a name="see-also"></a>См. также

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
