---
title: Класс CAnimationTimerEventHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: c94cb3849d4101365d137733c08135b86db23801
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518668"
---
# <a name="canimationtimereventhandler-class"></a>Класс CAnimationTimerEventHandler

Реализует обратный вызов, используемый API анимации, когда происходит событие расчета времени.

## <a name="syntax"></a>Синтаксис

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|Создает экземпляр класса `CAnimationTimerEventHandler` обратного вызова.|
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|Обрабатывает события, происходящие после завершения обновления анимации. (Переопределяет `CUIAnimationTimerEventHandlerBase::OnPostUpdate`.)|
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|Обрабатывает события, происходящие до начала обновления анимации. (Переопределяет `CUIAnimationTimerEventHandlerBase::OnPreUpdate`.)|
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|Обрабатывает события, происходящие, когда частота кадров отрисовки для анимации опускается ниже минимального нежелательно. (Переопределяет `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`.)|
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|Содержит указатель на контроллер анимации для маршрутизации события.|

## <a name="remarks"></a>Примечания

Этот обработчик событий создается и передается IUIAnimationTimer::SetTimerEventHandler при вызове CAnimationController::EnableAnimationTimerEventHandler.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="createinstance"></a>  CAnimationTimerEventHandler::CreateInstance

Создает экземпляр CAnimationTimerEventHandler обратного вызова.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>Параметры

*pAnimationController*<br/>
Указатель на контроллер анимации, который будет получать события.

*ppTimerEventHandler*

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="onpostupdate"></a>  CAnimationTimerEventHandler::OnPostUpdate

Обрабатывает события, происходящие после завершения обновления анимации.

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.

##  <a name="onpreupdate"></a>  CAnimationTimerEventHandler::OnPreUpdate

Обрабатывает события, происходящие до начала обновления анимации.

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.

##  <a name="onrenderingtooslow"></a>  CAnimationTimerEventHandler::OnRenderingTooSlow

Обрабатывает события, происходящие, когда частота кадров отрисовки для анимации опускается ниже минимального нежелательно.

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>Параметры

*кадров/с*

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.

##  <a name="setanimationcontroller"></a>  CAnimationTimerEventHandler::SetAnimationController

Содержит указатель на контроллер анимации для маршрутизации события.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Параметры

*pAnimationController*<br/>
Указатель на контроллер анимации, который будет получать события.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
