---
title: Класс ISpecifyPropertyPagesImpl
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 3f5db65d1c318677a630307f44533e51d63ec44d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272013"
---
# <a name="ispecifypropertypagesimpl-class"></a>Класс ISpecifyPropertyPagesImpl

Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) интерфейс.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `ISpecifyPropertyPagesImpl`.

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Заполняет значения подсчета массив UUID. Каждый UUID соответствует CLSID для одного из страницы свойств, которые могут отображаться в окне свойств объекта.|

## <a name="remarks"></a>Примечания

[ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) интерфейс позволяет клиенту получить список идентификаторов CLSID для страниц свойств, поддерживаемых объектом. Класс `ISpecifyPropertyPagesImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

> [!NOTE]
>  Не предоставляйте `ISpecifyPropertyPages` интерфейс, если объект поддерживает страницы свойств.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages

Заполняет массив [CAUUID](/windows/desktop/api/ocidl/ns-ocidl-tagcauuid) структуру с CLSID для страниц свойств, которые могут отображаться в окне свойств объекта.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Примечания

ATL использует сопоставление свойств объекта для получения каждого CLSID.

См. в разделе [ISpecifyPropertyPages::GetPages](/windows/desktop/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
