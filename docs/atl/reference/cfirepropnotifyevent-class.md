---
title: Класс CFirePropNotifyEvent
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 493bc00708d031f1bf7a4eb74d56e927a9c3f1dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245495"
---
# <a name="cfirepropnotifyevent-class"></a>Класс CFirePropNotifyEvent

Этот класс предоставляет методы для уведомления контейнера приемник об изменениях свойств элемента управления.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Статический) Уведомляет приемника контейнера, измененного свойства элемента управления.|
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Статический) Уведомляет контейнера приемника, который собираетесь изменить свойства элемента управления.|

## <a name="remarks"></a>Примечания

`CFirePropNotifyEvent` содержит два метода, уведомляющие приемника контейнера, который свойства элемента управления был изменен или изменением.

Если класс, реализующий элемент управления является производным от `IPropertyNotifySink`, `CFirePropNotifyEvent` методы вызываются при вызове `FireOnRequestEdit` или `FireOnChanged`. Если ваш класс элемента управления не является производным от `IPropertyNotifySink`, вызовы этих функций, верните значение s_ок.

Дополнительные сведения о создании элементов управления см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged

Уведомляет все подключенные [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейсы (на все точки подключения объекта), свойство указанного объекта изменилось.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
[in] Указатель на `IUnknown` объекта отправки уведомлений.

*dispID*<br/>
[in] Идентификатор измененного свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.

##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit

Уведомляет все подключенные [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейсы (на все точки подключения объекта), свойство указанного объекта будет изменена.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
[in] Указатель на `IUnknown` объекта отправки уведомлений.

*dispID*<br/>
[in] Идентификатор свойства изменением.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
