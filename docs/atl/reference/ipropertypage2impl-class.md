---
title: Класс IPropertyPage2Impl
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: bf76182242f7b76e3a2c18f85b72674e88afa737
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274780"
---
# <a name="ipropertypage2impl-class"></a>Класс IPropertyPage2Impl

Этот класс реализует `IUnknown` и наследует реализация по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IPropertyPage2Impl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|Указывает, какой элемент управления свойство получит фокус при активации страницы свойств. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

[IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) интерфейс расширяет [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) , добавив `EditProperty` метод. Этот метод позволяет клиенту, для выбора конкретного свойства в объект страницы свойств.

Класс `IPropertyPage2Impl` просто возвращает E_NOTIMPL для `IPropertyPage2::EditProperty`. Тем не менее, он наследует реализация по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

При создании страницы свойств класса обычно является производным от `IPropertyPageImpl`. Для дополнительной поддержки `IPropertyPage2`, измените определение класса и переопределить `EditProperty` метод.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="editproperty"></a>  IPropertyPage2Impl::EditProperty

Указывает, какой элемент управления свойство получит фокус при активации страницы свойств.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage2::EditProperty](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage2-editproperty) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
