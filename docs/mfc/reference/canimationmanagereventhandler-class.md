---
title: Класс CAnimationManagerEventHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
ms.openlocfilehash: 497b6e0f5bdeb817eccb0bb42f66763a97da2af0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445738"
---
# <a name="canimationmanagereventhandler-class"></a>Класс CAnimationManagerEventHandler

Реализует обратный вызов, используемый API анимации при изменении состояния диспетчера анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](#canimationmanagereventhandler)|Создает объект `CAnimationManagerEventHandler`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationManagerEventHandler::CreateInstance](#createinstance)|Создает экземпляр класса `CAnimationManagerEventHandler` объекта.|
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|Вызывается при изменении состояния диспетчера анимации. (Переопределяет `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`.)|
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|Содержит указатель на контроллер анимации для маршрутизации события.|

## <a name="remarks"></a>Примечания

Этот обработчик событий создается и передается методу IUIAnimationManager::SetManagerEventHandler, при вызове CAnimationController::EnableAnimationManagerEvent.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="canimationmanagereventhandler"></a>  CAnimationManagerEventHandler::CAnimationManagerEventHandler

Требуется Visual Studio 2010 с пакетом обновления 1 (SP1).

Создает объект CAnimationManagerEventHandler.

```
CAnimationManagerEventHandler();
```

##  <a name="createinstance"></a>  CAnimationManagerEventHandler::CreateInstance

Требуется Visual Studio 2010 с пакетом обновления 1 (SP1).

Создает экземпляр объекта CAnimationManagerEventHandler.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>Параметры

*pAnimationController*<br/>
Указатель на контроллер анимации, который будет получать события.

*ppManagerEventHandler*<br/>
Выходные данные. Если метод выполняется успешно, он содержит указатель на COM-объект, обрабатывающий обновления состояния диспетчера анимации.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="onmanagerstatuschanged"></a>  CAnimationManagerEventHandler::OnManagerStatusChanged

Требуется Visual Studio 2010 с пакетом обновления 1 (SP1).

Вызывается при изменении состояния диспетчера анимации.

```
IFACEMETHOD(OnManagerStatusChanged)(
  UI_ANIMATION_MANAGER_STATUS newStatus,
  UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Параметры

*newStatus*<br/>
Новое состояние.

*previousStatus*<br/>
Предыдущее состояние.

### <a name="return-value"></a>Возвращаемое значение

Текущая реализация всегда возвращает значение S_OK;

##  <a name="setanimationcontroller"></a>  CAnimationManagerEventHandler::SetAnimationController

Требуется Visual Studio 2010 с пакетом обновления 1 (SP1).

Содержит указатель на контроллер анимации для маршрутизации события.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Параметры

*pAnimationController*<br/>
Указатель на контроллер анимации, который будет получать события.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
