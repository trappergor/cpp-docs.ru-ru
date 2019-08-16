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
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496936"
---
# <a name="cfirepropnotifyevent-class"></a>Класс Кфирепропнотифевент

Этот класс предоставляет методы для уведомления приемника контейнера об изменениях свойств элемента управления.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кфирепропнотифевент:: Фиреончанжед](#fireonchanged)|Статически Сообщает приемнику контейнера, что свойство элемента управления изменилось.|
|[Кфирепропнотифевент:: Фиреонрекуестедит](#fireonrequestedit)|Статически Уведомляет приемник контейнера, что свойство элемента управления собирается измениться.|

## <a name="remarks"></a>Примечания

`CFirePropNotifyEvent`содержит два метода, уведомляющих приемник контейнера о том, что свойство элемента управления изменилось или будет изменено.

Если класс `IPropertyNotifySink` `FireOnRequestEdit` , реализующий элемент управления, является производным от, `FireOnChanged` методывызываютсяпривызовеметодаили.`CFirePropNotifyEvent` Если класс элемента управления не является производным `IPropertyNotifySink`от, вызовы этих функций возвращают значение S_OK.

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
окне `IUnknown` Указатель на объект объекта, отправляющего уведомление.

*dispID*<br/>
окне Идентификатор измененного свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.

##  <a name="fireonrequestedit"></a>Кфирепропнотифевент:: Фиреонрекуестедит

Уведомляет все подключенные интерфейсы [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) (в каждой точке соединения объекта) о том, что необходимо изменить указанное свойство объекта.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
окне `IUnknown` Указатель на объект объекта, отправляющего уведомление.

*dispID*<br/>
окне Идентификатор свойства, которое необходимо изменить.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
