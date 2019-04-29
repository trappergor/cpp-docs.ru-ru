---
title: Класс CInterpolatorBase
ms.date: 11/04/2016
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
ms.openlocfilehash: 379aa5607e459ad8acfd99c5899315afb84ac4a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392665"
---
# <a name="cinterpolatorbase-class"></a>Класс CInterpolatorBase

Реализует обратный вызов, используемый API анимации, когда требуется рассчитать новое значение переменной анимации.

## <a name="syntax"></a>Синтаксис

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Создает `CInterpolatorBase` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CInterpolatorBase::CreateInstance](#createinstance)|Создает экземпляр класса `CInterpolatorBase` и содержит указатель на пользовательские интерполятора, который будет обрабатывать события.|
|[CInterpolatorBase::GetDependencies](#getdependencies)|Возвращает зависимости интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::GetDependencies`.)|
|[CInterpolatorBase::GetDuration](#getduration)|Возвращает длительность интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::GetDuration`.)|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Получает конечное значение, к которому ведет интерполятора. (Переопределяет `CUIAnimationInterpolatorBase::GetFinalValue`.)|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Осуществляет интерполяцию значение с указанным смещением (переопределяет `CUIAnimationInterpolatorBase::InterpolateValue`.)|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Осуществляет интерполяцию скорость с указанным смещением (переопределяет `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Содержит указатель на пользовательские интерполятора, который будет обрабатывать события.|
|[CInterpolatorBase::SetDuration](#setduration)|Задает длительность интерполятора (переопределяет `CUIAnimationInterpolatorBase::SetDuration`.)|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Задает начальное значение и скорости интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|

## <a name="remarks"></a>Примечания

Этот обработчик создается и передается `IUIAnimationTransitionFactory::CreateTransition` при `CCustomTransition` объект создается как часть процесса инициализации анимации (создано `CAnimationController::AnimateGroup`). Обычно не нужно использовать его напрямую, он просто свою очередь, перенаправляет все события для `CCustomInterpolator`-производного класса, указатель передается конструктору `CCustomTransition`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cinterpolatorbase"></a>  CInterpolatorBase::CInterpolatorBase

Создает объект CInterpolatorBase.

```
CInterpolatorBase();
```

##  <a name="createinstance"></a>  CInterpolatorBase::CreateInstance

Создает экземпляр класса CInterpolatorBase и сохраняет указатель на пользовательские интерполятора, который будет обрабатывать события.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Параметры

*pInterpolator*<br/>
Указатель на пользовательские интерполятор.

*ppHandler*<br/>
Выходные данные. Содержит указатель на экземпляр CInterpolatorBase при возврате функции.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="getdependencies"></a>  CInterpolatorBase::GetDependencies

Возвращает зависимости интерполятор.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Параметры

*initialValueDependencies*<br/>
Выходные данные. Аспекты интерполятора, которые зависят от начального значения, передаваемые от SetInitialValueAndVelocity.

*initialVelocityDependencies*<br/>
Выходные данные. Аспекты интерполятора, которые зависят от начальной скорости, передаваемые от SetInitialValueAndVelocity.

*durationDependencies*<br/>
Выходные данные. Аспекты интерполятора, которые зависят от длительности, передаваемые от SetDuration.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не задано или пользовательская реализация возвращает значение FALSE из метода GetDependencies.

##  <a name="getduration"></a>  CInterpolatorBase::GetDuration

Возвращает длительность интерполятор.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Выходные данные. Длительность перехода, в секундах.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не задано или пользовательская реализация возвращает значение FALSE из метода GetDuration.

##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue

Получает конечное значение, к которому ведет интерполятора.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Выходные данные. Конечное значение переменной в конце перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не задано или пользовательская реализация возвращает значение FALSE из метода GetFinalValue.

##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue

Осуществляет интерполяцию значение с указанным смещением

```
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*offset*<br/>
Смещение от начала перехода. Смещение всегда равно, больше или равно нулю и меньше, чем длительность перехода. Этот метод не вызывается, если длительность перехода равна нулю.

*value*<br/>
Выходные данные. Интерполированное значение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не задано или пользовательская реализация возвращает значение FALSE из метода InterpolateValue.

##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity

Осуществляет интерполяцию скорости, начиная с указанной позиции

```
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```

### <a name="parameters"></a>Параметры

*offset*<br/>
Смещение от начала перехода. Смещение всегда больше или равно нулю и меньше или равно длительности перехода. Этот метод не вызывается, если длительность перехода равна нулю.

*Скорость*<br/>
Выходные данные. Скорость переменной по смещению.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не задано или пользовательская реализация возвращает значение FALSE из метода InterpolateVelocity.

##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator

Содержит указатель на пользовательские интерполятора, который будет обрабатывать события.

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Параметры

*pInterpolator*<br/>
Указатель на пользовательские интерполятор.

##  <a name="setduration"></a>  CInterpolatorBase::SetDuration

Задает длительность интерполятора

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не задано или пользовательская реализация возвращает значение FALSE из метода SetDuration.

##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity

Задает начальное значение и скорости интерполятор.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue,
  __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Параметры

*Начальное значение*<br/>
Значение переменной в начале перехода.

*initialVelocity*<br/>
Скорость, переменной в начале перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не задано или пользовательская реализация возвращает значение FALSE из метода SetInitialValueAndVelocity.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
