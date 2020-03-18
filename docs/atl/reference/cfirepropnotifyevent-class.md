---
title: Класс Кфирепропнотифевент
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
ms.openlocfilehash: 694127ceccc1d1b55e5da9abca799dff77dcfc60
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423270"
---
# <a name="cfirepropnotifyevent-class"></a>Класс Кфирепропнотифевент

Этот класс предоставляет методы для уведомления приемника контейнера об изменениях свойств элемента управления.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кфирепропнотифевент:: Фиреончанжед](#fireonchanged)|Статически Сообщает приемнику контейнера, что свойство элемента управления изменилось.|
|[Кфирепропнотифевент:: Фиреонрекуестедит](#fireonrequestedit)|Статически Уведомляет приемник контейнера, что свойство элемента управления собирается измениться.|

## <a name="remarks"></a>Remarks

`CFirePropNotifyEvent` имеет два метода, которые уведомляют приемник контейнера о том, что свойство элемента управления изменилось или будет изменяться.

Если класс, реализующий элемент управления, является производным от `IPropertyNotifySink`, методы `CFirePropNotifyEvent` вызываются при вызове `FireOnRequestEdit` или `FireOnChanged`. Если класс элемента управления не является производным от `IPropertyNotifySink`, вызовы этих функций возвращают S_OK.

Дополнительные сведения о создании элементов управления см. в [учебнике по ATL](../../atl/active-template-library-atl-tutorial.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="fireonchanged"></a>Кфирепропнотифевент:: Фиреончанжед

Уведомляет все подключенные интерфейсы [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) (в каждой точке соединения объекта) об изменении указанного свойства объекта.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Указатель на `IUnknown` объекта, отправляющего уведомление.

*dispID*<br/>
окне Идентификатор измененного свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.

##  <a name="fireonrequestedit"></a>Кфирепропнотифевент:: Фиреонрекуестедит

Уведомляет все подключенные интерфейсы [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) (в каждой точке соединения объекта) о том, что необходимо изменить указанное свойство объекта.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне Указатель на `IUnknown` объекта, отправляющего уведомление.

*dispID*<br/>
окне Идентификатор свойства, которое необходимо изменить.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../../atl/atl-class-overview.md)
