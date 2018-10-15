---
title: Класс CAccelerateDecelerateTransition | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0133a24b5253baa4d7292cc54d02df5201abd63
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334594"
---
# <a name="cacceleratedeceleratetransition-class"></a>Класс CAccelerateDecelerateTransition

Реализует переход между ускорением и замедлением.

## <a name="syntax"></a>Синтаксис

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Создает объект перехода.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAccelerateDecelerateTransition::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Доля времени, затраченный на ускорение длительности.|
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Доля времени, затраченного на замедление длительности.|
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Длительность перехода.|
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Значение переменной анимации в конце перехода.|

## <a name="remarks"></a>Примечания

Во время accelerate-Замедление перехода, ускоряет переменной анимации и затем замедляется за период времени перехода, заканчивая указанное значение. Можно управлять как быстро переменной ускоряется и замедляется независимо друг от друга, путем указания различных ускорение и замедление коэффициенты. Если Начальная скорость равен нулю, отношение ускорение равно дробное число длительность, переменная будет потрачена на ускорение; Аналогичным образом с замедление отношение. Если Начальная скорость имеет ненулевое значение, то часть времени между скорость достижения нуля и в конце перехода. Отношение ускорение и замедление отношение сумма должна составлять более 1.0. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition

Создает объект перехода.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

*finalValue*<br/>
Значение переменной анимации в конце перехода.

*accelerationRatio*<br/>
Доля времени, затраченный на ускорение длительности.

*decelerationRatio*<br/>
Доля времени, затраченного на замедление длительности.

##  <a name="create"></a>  CAccelerateDecelerateTransition::Create

Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на [IUIAnimationTransitionLibrary интерфейс](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.

##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio

Доля времени, затраченный на ускорение длительности.

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio

Доля времени, затраченного на замедление длительности.

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
