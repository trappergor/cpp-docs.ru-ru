---
title: Класс Иперпропертибровсингимпл
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: 263f6826ac921d864dee646ef063c8b456b00af1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495719"
---
# <a name="iperpropertybrowsingimpl-class"></a>Класс Иперпропертибровсингимпл

Этот класс реализует `IUnknown` и позволяет клиенту обращаться к данным на страницах свойств объекта.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IPerPropertyBrowsingImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иперпропертибровсингимпл:: Жетдисплайстринг](#getdisplaystring)|Извлекает строку, описывающую заданное свойство.|
|[Иперпропертибровсингимпл:: Жетпредефинедстрингс](#getpredefinedstrings)|Извлекает массив строк, соответствующий значениям, которые может принимать данное свойство.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Извлекает объект типа VARIANT, содержащий значение свойства, идентифицируемого по заданному идентификатору DISPID. Идентификатор DISPID связан с именем строки, полученным из `GetPredefinedStrings`. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иперпропертибровсингимпл:: Маппропертитопаже](#mappropertytopage)|Извлекает идентификатор CLSID страницы свойств, связанной с данным свойством.|

## <a name="remarks"></a>Примечания

Интерфейс [иперпропертибровсинг](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing) позволяет клиенту получить доступ к информации на страницах свойств объекта. Класс `IPerPropertyBrowsingImpl` предоставляет реализацию этого интерфейса по умолчанию и реализует `IUnknown` , отправляя сведения в устройство дампа в отладочных сборках.

> [!NOTE]
>  Если вы используете Microsoft Access в качестве приложения контейнера, необходимо создать класс, производный от `IPerPropertyBrowsingImpl`. В противном случае Access не будет загружать элемент управления.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="getdisplaystring"></a>Иперпропертибровсингимпл:: Жетдисплайстринг

Извлекает строку, описывающую заданное свойство.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Примечания

См. раздел [иперпропертибровсинг:: жетдисплайстринг](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) в Windows SDK.

##  <a name="getpredefinedstrings"></a>Иперпропертибровсингимпл:: Жетпредефинедстрингс

Заполняет каждый массив нулевыми элементами.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Возвращаемое значение

Реализация [жетпредефинедвалуе](#getpredefinedvalue) в библиотеке ATL ВОЗВРАЩАЕТ значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [иперпропертибровсинг:: жетпредефинедстрингс](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) в Windows SDK.

##  <a name="getpredefinedvalue"></a>Иперпропертибровсингимпл:: Жетпредефинедвалуе

Извлекает объект типа VARIANT, содержащий значение свойства, идентифицируемого по заданному идентификатору DISPID. Идентификатор DISPID связан с именем строки, полученным из `GetPredefinedStrings`.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

Реализация [жетпредефинедстрингс](#getpredefinedstrings) библиотеки ATL не извлекает соответствующие строки.

См. раздел [иперпропертибровсинг:: жетпредефинедвалуе](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) в Windows SDK.

##  <a name="mappropertytopage"></a>Иперпропертибровсингимпл:: Маппропертитопаже

Извлекает идентификатор CLSID страницы свойств, связанной с указанным свойством.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Примечания

Для получения этих сведений в ATL используется схема свойств объекта.

См. раздел [иперпропертибровсинг:: маппропертитопаже](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
