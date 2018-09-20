---
title: Класс CCubicTransition | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2bd07d8f57396da78ce19cb5ac568d651f71459b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398076"
---
# <a name="ccubictransition-class"></a>Класс CCubicTransition

Инкапсулирует кубический переход.

## <a name="syntax"></a>Синтаксис

```
class CCubicTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCubicTransition::CCubicTransition](#ccubictransition)|Создает объект перехода и инициализирует его параметры.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCubicTransition::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CCubicTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|
|[CCubicTransition::m_dblFinalVelocity](#m_dblfinalvelocity)|Скорость, переменной в конце перехода.|
|[CCubicTransition::m_duration](#m_duration)|Длительность перехода.|

## <a name="remarks"></a>Примечания

Во время третьего перехода значение переменной анимации изменяется от его начального значения на указанного конечное значение за период времени перехода, заканчивая с указанной скоростью. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="ccubictransition"></a>  CCubicTransition::CCubicTransition

Создает объект перехода и инициализирует его параметры.

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

*finalValue*<br/>
Значение переменной анимации в конце перехода.

*finalVelocity*<br/>
Скорость, переменной в конце перехода.

##  <a name="create"></a>  CCubicTransition::Create

Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на [IUIAnimationTransitionLibrary интерфейс](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.

##  <a name="m_dblfinalvalue"></a>  CCubicTransition::m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>  CCubicTransition::m_dblFinalVelocity

Скорость, переменной в конце перехода.

```
DOUBLE m_dblFinalVelocity;
```

##  <a name="m_duration"></a>  CCubicTransition::m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
