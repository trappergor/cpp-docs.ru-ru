---
title: Класс IPerPropertyBrowsingImpl
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
ms.openlocfilehash: 54c475e736425718e954b0e954ea2b327d938556
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299465"
---
# <a name="iperpropertybrowsingimpl-class"></a>Класс IPerPropertyBrowsingImpl

Этот класс реализует `IUnknown` и позволяет клиенту получать доступ к сведениям на страницах свойств объекта.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IPerPropertyBrowsingImpl`.

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Извлекает строку, описывающую данное свойство.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Извлекает массив строк, соответствующее значениям, которые могут принимать заданного свойства.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Извлекает значение VARIANT, содержащий значение свойства, идентифицируемого по заданной DISPID. Идентификатор DISPID связан с данным именем строки, полученные из `GetPredefinedStrings`. Реализация ATL возвращает E_NOTIMPL.|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Извлекает идентификатор CLSID страницы свойств, сопоставленный данному свойству.|

## <a name="remarks"></a>Примечания

[IPerPropertyBrowsing](/windows/desktop/api/ocidl/nn-ocidl-iperpropertybrowsing) интерфейс позволяет клиенту получать доступ к сведениям на страницах свойств объекта. Класс `IPerPropertyBrowsingImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

> [!NOTE]
>  Если вы используете Microsoft Access в качестве приложения-контейнера, должен быть производным от класса `IPerPropertyBrowsingImpl`. В противном случае доступ не загружает элемент управления.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString

Извлекает строку, описывающую данное свойство.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPerPropertyBrowsing::GetDisplayString](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) в Windows SDK.

##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings

Заполняет каждый массив с нулевыми элементами.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Возвращаемое значение

Реализация библиотеки ATL [GetPredefinedValue](#getpredefinedvalue) возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IPerPropertyBrowsing::GetPredefinedStrings](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) в Windows SDK.

##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue

Извлекает значение VARIANT, содержащий значение свойства, идентифицируемого по заданной DISPID. Идентификатор DISPID связан с данным именем строки, полученные из `GetPredefinedStrings`.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

Реализация библиотеки ATL [GetPredefinedStrings](#getpredefinedstrings) нет соответствующей строки.

См. в разделе [IPerPropertyBrowsing::GetPredefinedValue](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) в Windows SDK.

##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage

Извлекает идентификатор CLSID страницы свойств, связанных с указанным свойством.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Примечания

ATL использует сопоставление свойств объекта для получения этих сведений.

См. в разделе [IPerPropertyBrowsing::MapPropertyToPage](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
