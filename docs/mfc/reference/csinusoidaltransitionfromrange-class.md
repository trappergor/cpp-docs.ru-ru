---
title: Класс CSinusoidalTransitionFromRange
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
ms.openlocfilehash: df360493413e850f4c0fcee41c925cd256c16dad
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283817"
---
# <a name="csinusoidaltransitionfromrange-class"></a>Класс CSinusoidalTransitionFromRange

Инкапсулирует переход в диапазоне синусоиды с заданной амплитудой колебаний.

## <a name="syntax"></a>Синтаксис

```
class CSinusoidalTransitionFromRange : public CBaseTransition;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Создает объект перехода.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CSinusoidalTransitionFromRange::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|Значение переменной анимации в пиковое значение переход wave.|
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|Значение переменной анимации с помощью средства переход wave.|
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|Длительность перехода.|
|[CSinusoidalTransitionFromRange::m_period](#m_period)|Период колебаний из wave переход в секундах.|
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|Наклон в начале перехода.|

## <a name="remarks"></a>Примечания

Значение переменной анимации используется от указанное минимальное и максимальное значение за весь период времени в диапазоне синусоиды перехода. Наклон параметр используется для устранения неоднозначности между двух возможных синусоидальных волн, указанных другими параметрами. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="create"></a>  CSinusoidalTransitionFromRange::Create

Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая отвечает за создание стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.

##  <a name="csinusoidaltransitionfromrange"></a>  CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange

Создает объект перехода.

```
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblMinimumValue,
    DOUBLE dblMaximumValue,
    UI_ANIMATION_SECONDS period,
    UI_ANIMATION_SLOPE slope);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

*dblMinimumValue*<br/>
Значение переменной анимации с помощью средства переход wave.

*dblMaximumValue*<br/>
Значение переменной анимации в пиковое значение переход wave.

*Период*<br/>
Период колебаний из wave переход в секундах.

*Наклон*<br/>
Наклон в начале перехода.

##  <a name="m_dblmaximumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMaximumValue

Значение переменной анимации в пиковое значение переход wave.

```
DOUBLE m_dblMaximumValue;
```

##  <a name="m_dblminimumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMinimumValue

Значение переменной анимации с помощью средства переход wave.

```
DOUBLE m_dblMinimumValue;
```

##  <a name="m_duration"></a>  CSinusoidalTransitionFromRange::m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_period"></a>  CSinusoidalTransitionFromRange::m_period

Период колебаний из wave переход в секундах.

```
UI_ANIMATION_SECONDS m_period;
```

##  <a name="m_slope"></a>  CSinusoidalTransitionFromRange::m_slope

Наклон в начале перехода.

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
