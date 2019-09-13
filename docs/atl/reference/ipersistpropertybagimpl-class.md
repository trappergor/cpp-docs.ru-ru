---
title: Класс Иперсистпропертибагимпл
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
ms.openlocfilehash: 15b9c9738d921c4c6f7837f9280c6dd6b09392d6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495778"
---
# <a name="ipersistpropertybagimpl-class"></a>Класс Иперсистпропертибагимпл

Этот класс реализует `IUnknown` и позволяет объекту сохранять свои свойства в контейнере свойств, предоставляемом клиентом.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IPersistPropertyBagImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иперсистпропертибагимпл::, ClassID](#getclassid)|Получает CLSID объекта.|
|[Иперсистпропертибагимпл:: InitNew](#initnew)|Инициализирует вновь созданный объект. Реализация ATL возвращает значение S_OK.|
|[Иперсистпропертибагимпл:: Load](#load)|Загружает свойства объекта из контейнера свойств, предоставляемого клиентом.|
|[Иперсистпропертибагимпл:: Save](#save)|Сохраняет свойства объекта в контейнере свойств, предоставляемом клиентом.|

## <a name="remarks"></a>Примечания

Интерфейс [IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) позволяет объекту сохранять свои свойства в контейнере свойств, предоставляемом клиентом. Класс `IPersistPropertyBagImpl` предоставляет реализацию этого интерфейса по умолчанию и реализует `IUnknown` , отправляя сведения в устройство дампа в отладочных сборках.

`IPersistPropertyBag`работает в сочетании с [ипропертибаг](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) и [иеррорлог](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\)). Эти два последних интерфейса должны быть реализованы клиентом. С `IPropertyBag`помощью Клиент сохраняет и загружает отдельные свойства объекта. С `IErrorLog`помощью объект и клиент могут сообщать об обнаруженных ошибках.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="getclassid"></a>Иперсистпропертибагимпл::, ClassID

Получает CLSID объекта.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Примечания

См. [IPersist:: ClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) в Windows SDK.

##  <a name="initnew"></a>Иперсистпропертибагимпл:: InitNew

Инициализирует вновь созданный объект.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [IPersistPropertyBag:: InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) в Windows SDK.

##  <a name="load"></a>Иперсистпропертибагимпл:: Load

Загружает свойства объекта из контейнера свойств, предоставляемого клиентом.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Примечания

Для получения этих сведений в ATL используется схема свойств объекта.

См. раздел [IPersistPropertyBag:: Load](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) в Windows SDK.

##  <a name="save"></a>Иперсистпропертибагимпл:: Save

Сохраняет свойства объекта в контейнере свойств, предоставляемом клиентом.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Примечания

Для хранения этих сведений в ATL используется схема свойств объекта. По умолчанию этот метод сохраняет все свойства независимо от значения *фсавеаллпропертиес*.

См. раздел [IPersistPropertyBag:: Save](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) в Windows SDK.

## <a name="see-also"></a>См. также

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
