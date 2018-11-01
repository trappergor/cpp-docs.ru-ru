---
title: Класс CAnimationStoryboardEventHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
ms.openlocfilehash: b5dbe10f0fd80956b395ec385969750c3ee0c05b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632873"
---
# <a name="canimationstoryboardeventhandler-class"></a>Класс CAnimationStoryboardEventHandler

Реализует обратный вызов, используемый API анимации при изменении состояния или обновлении раскадровки.

## <a name="syntax"></a>Синтаксис

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Создает объект `CAnimationStoryboardEventHandler`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CreateInstance](#createinstance)|Создает экземпляр класса `CAnimationStoryboardEventHandler` обратного вызова.|
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Обрабатывает `OnStoryboardStatusChanged` событий, которые происходят при изменении состояния раскадровки (переопределяет `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.)|
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|Обрабатывает `OnStoryboardUpdated` событий, которые происходят при обновлении раскадровки (переопределяет `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.)|
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|Содержит указатель на контроллер анимации для маршрутизации события.|

## <a name="remarks"></a>Примечания

Этот обработчик событий создается и передается `IUIAnimationStoryboard::SetStoryboardEventHandler` при вызове метода `CAnimationController::EnableStoryboardEventHandler`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="canimationstoryboardeventhandler"></a>  CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler

Создает объект CAnimationStoryboardEventHandler.

```
CAnimationStoryboardEventHandler();
```

##  <a name="createinstance"></a>  CAnimationStoryboardEventHandler::CreateInstance

Создает экземпляр CAnimationStoryboardEventHandler обратного вызова.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>Параметры

*pAnimationController*<br/>
Указатель на контроллер анимации, который будет получать события.

*ppHandler*

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="onstoryboardstatuschanged"></a>  CAnimationStoryboardEventHandler::OnStoryboardStatusChanged

Обрабатывает OnStoryboardStatusChanged событий, которые происходят при изменении состояния раскадровки

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Параметры

*раскадровки*<br/>
Указатель на раскадровки, состояние которого изменилось.

*newStatus*<br/>
Указывает новое состояние раскадровки.

*previousStatus*<br/>
Указывает прежнее состояние раскадровки.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.

##  <a name="onstoryboardupdated"></a>  CAnimationStoryboardEventHandler::OnStoryboardUpdated

Обрабатывает OnStoryboardUpdated события, возникающие при обновлении раскадровки

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>Параметры

*раскадровки*<br/>
Указатель на раскадровку, которая была обновлена.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.

##  <a name="setanimationcontroller"></a>  CAnimationStoryboardEventHandler::SetAnimationController

Содержит указатель на контроллер анимации для маршрутизации события.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Параметры

*pAnimationController*<br/>
Указатель на контроллер анимации, который будет получать события.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
