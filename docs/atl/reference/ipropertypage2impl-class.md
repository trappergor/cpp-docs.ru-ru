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
ms.openlocfilehash: 5ec6cb2f4fc6931a1bec429068b558bf7ac1906e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495599"
---
# <a name="ipropertypage2impl-class"></a>Класс IPropertyPage2Impl

Этот класс реализует `IUnknown` и наследует реализацию [ипропертипажеимпл](../../atl/reference/ipropertypageimpl-class.md)по умолчанию.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IPropertyPage2Impl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IPropertyPage2Impl:: Едитпроперти](#editproperty)|Указывает, какой элемент управления будет получать фокус при активации страницы свойств. Реализация ATL возвращает значение E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Интерфейс [IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) расширяет [ипропертипаже](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) `EditProperty` , добавляя метод. Этот метод позволяет клиенту выбрать определенное свойство в объекте страницы свойств.

Класс `IPropertyPage2Impl` просто возвращает значение E_NOTIMPL `IPropertyPage2::EditProperty`для. Однако он наследует реализацию по умолчанию [ипропертипажеимпл](../../atl/reference/ipropertypageimpl-class.md) и реализуется `IUnknown` путем отправки информации в устройство дампа в отладочных сборках.

При создании страницы свойств класс обычно является производным от `IPropertyPageImpl`. Чтобы обеспечить лишнюю поддержку `IPropertyPage2`, измените определение класса и `EditProperty` Переопределите метод.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPropertyPage`

[ипропертипажеимпл](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="editproperty"></a>IPropertyPage2Impl:: Едитпроперти

Указывает, какой элемент управления будет получать фокус при активации страницы свойств.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [IPropertyPage2:: едитпроперти](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
