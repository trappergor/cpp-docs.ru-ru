---
title: Класс CAnimationVariableChangeHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 7f45fdad00bacf56e2ee8c30b76e99d626902534
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377084"
---
# <a name="canimationvariablechangehandler-class"></a>Класс CAnimationVariableChangeHandler

Реализует обратный вызов, используемый API анимации при изменении значения переменной анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Формирует объект `CAnimationVariableChangeHandler`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|Создает экземпляр `CAnimationVariableChangeHandler` объекта.|
|[CanimationvariablevariableChangehandler::OnvalueChanged](#onvaluechanged)|Вызывается при изменении значения переменной анимации. (Переопределяет `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.)|
|[CAnimationVariableChangeChangeHandler::SetAnimationController](#setanimationcontroller)|Хранит указатель контроллера анимации для маршрутизатора событий.|

## <a name="remarks"></a>Remarks

Обработчик событий создается `IUIAnimationVariable::SetVariableChangeHandler` и передается `CAnimationVariable::EnableValueChangedEvent` `CAnimationBaseObject::EnableValueChangedEvent` методу, когда вы вызываете или (что позволяет этому событию для всех переменных анимации, инкапсулированных в объекте анимации).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a>CanimationvariablevariableChangehandler::OnvalueChanged

Вызывается при изменении значения переменной анимации.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>Параметры

*Раскадровки*<br/>
Раскадровка, онимающая переменную.

*переменная*<br/>
Обновленная переменная анимации.

*newValue*<br/>
Новое значение.

*предыдущаястоимость*<br/>
Предыдущее значение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. В противном случае он возвращает код ошибки HRESULT.

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a>CAnimationVariableChangeChangeHandler::SetAnimationController

Хранит указатель контроллера анимации для маршрутизатора событий.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Параметры

*pAnimationКонтроллер*<br/>
Указатель на контроллер анимации, который будет получать события.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
