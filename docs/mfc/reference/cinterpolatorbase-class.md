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
ms.openlocfilehash: d1fc675b1014ab9a099e8310b52b7458f2bff65f
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916200"
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
|[Цинтерполаторбасе:: Цинтерполаторбасе](#cinterpolatorbase)|`CInterpolatorBase` Конструирует объект.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Цинтерполаторбасе:: CreateInstance](#createinstance)|Создает экземпляр `CInterpolatorBase` и сохраняет указатель на настраиваемую интерполяцию, которая будет обрабатывать события.|
|[Цинтерполаторбасе:: Dependencies](#getdependencies)|Возвращает зависимости интерполяции. (Переопределяет `CUIAnimationInterpolatorBase::GetDependencies`.)|
|[Цинтерполаторбасе:: длит](#getduration)|Возвращает длительность интерполяции. (Переопределяет `CUIAnimationInterpolatorBase::GetDuration`.)|
|[Цинтерполаторбасе:: Жетфиналвалуе](#getfinalvalue)|Возвращает конечное значение, которое вызывает интерполяцию. (Переопределяет `CUIAnimationInterpolatorBase::GetFinalValue`.)|
|[Цинтерполаторбасе:: Интерполатевалуе](#interpolatevalue)|Выполняет интерполяцию значения в заданном смещении ( `CUIAnimationInterpolatorBase::InterpolateValue`переопределения.)|
|[Цинтерполаторбасе:: ИнтерполатевелоЦити](#interpolatevelocity)|Интерполирует скорость в заданном смещении (переопределения `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|
|[Цинтерполаторбасе:: Сеткустоминтерполатор](#setcustominterpolator)|Хранит указатель на пользовательский интерполяций, который будет обрабатывать события.|
|[Цинтерполаторбасе:: Сетдуратион](#setduration)|Задает длительность интерполяции (переопределения `CUIAnimationInterpolatorBase::SetDuration`.)|
|[Цинтерполаторбасе:: СетинитиалвалуеандвелоЦити](#setinitialvalueandvelocity)|Задает начальное значение и скорость для интерполяции. (Переопределяет `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|

## <a name="remarks"></a>Примечания

Этот обработчик создается и передается `IUIAnimationTransitionFactory::CreateTransition` в, `CCustomTransition` когда объект создается как часть процесса инициализации анимации (запускается с помощью `CAnimationController::AnimateGroup`). Обычно этот класс не требуется использовать напрямую, он просто перенадает все события в `CCustomInterpolator`производный класс, указатель которого передан `CCustomTransition`конструктору.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cinterpolatorbase"></a>Цинтерполаторбасе:: Цинтерполаторбасе

Конструирует объект Цинтерполаторбасе.

```
CInterpolatorBase();
```

##  <a name="createinstance"></a>Цинтерполаторбасе:: CreateInstance

Создает экземпляр Цинтерполаторбасе и сохраняет указатель на настраиваемую интерполяцию, которая будет обрабатывать события.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Параметры

*пинтерполатор*<br/>
Указатель на настраиваемый интерполяцию.

*пфандлер*<br/>
Проверки. Содержит указатель на экземпляр Цинтерполаторбасе при возврате функции.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="getdependencies"></a>Цинтерполаторбасе:: Dependencies

Возвращает зависимости интерполяции.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Параметры

*инитиалвалуедепенденЦиес*<br/>
Проверки. Аспекты интерполяции, зависящие от первоначального значения, переданного в СетинитиалвалуеандвелоЦити.

*инитиалвелоЦитидепенденЦиес*<br/>
Проверки. Аспекты интерполяции, зависящие от начальной скорости, передаваемой в СетинитиалвалуеандвелоЦити.

*дуратиондепенденЦиес*<br/>
Проверки. Аспекты интерполяции, зависящие от длительности, переданной в Сетдуратион.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, он возвращает значение S_OK. Он возвращает значение E_FAIL, если Ккустоминтерполатор не задано, или пользовательская реализация возвращает FALSE из метода DEPENDENCIES.

##  <a name="getduration"></a>Цинтерполаторбасе:: длит

Возвращает длительность интерполяции.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Параметры

*длитель*<br/>
Проверки. Длительность перехода в секундах.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, он возвращает значение S_OK. Он возвращает значение E_FAIL, если Ккустоминтерполатор не задано, или пользовательская реализация возвращает FALSE из метода IsFalse.

##  <a name="getfinalvalue"></a>Цинтерполаторбасе:: Жетфиналвалуе

Возвращает конечное значение, которое вызывает интерполяцию.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Проверки. Конечное значение переменной в конце перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, он возвращает значение S_OK. Он возвращает значение E_FAIL, если Ккустоминтерполатор не задано, или пользовательская реализация возвращает FALSE из метода Жетфиналвалуе.

##  <a name="interpolatevalue"></a>Цинтерполаторбасе:: Интерполатевалуе

Выполняет интерполяцию значения по заданному смещению

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*offset*<br/>
Смещение от начала перехода. Смещение всегда больше или равно нулю и меньше, чем длительность перехода. Этот метод не вызывается, если длительность перехода равна нулю.

*value*<br/>
Проверки. Значение интерполяции.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, он возвращает значение S_OK. Он возвращает значение E_FAIL, если Ккустоминтерполатор не задано, или пользовательская реализация возвращает FALSE из метода Интерполатевалуе.

##  <a name="interpolatevelocity"></a>Цинтерполаторбасе:: ИнтерполатевелоЦити

Интерполяция скорости в заданном смещении

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>Параметры

*offset*<br/>
Смещение от начала перехода. Смещение всегда больше или равно нулю и меньше или равно длительности перехода. Этот метод не вызывается, если длительность перехода равна нулю.

*скорость*<br/>
Проверки. Скорость переменной в смещении.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, он возвращает значение S_OK. Он возвращает значение E_FAIL, если Ккустоминтерполатор не задано, или пользовательская реализация возвращает FALSE из метода ИнтерполатевелоЦити.

##  <a name="setcustominterpolator"></a>Цинтерполаторбасе:: Сеткустоминтерполатор

Хранит указатель на пользовательский интерполяций, который будет обрабатывать события.

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Параметры

*пинтерполатор*<br/>
Указатель на настраиваемый интерполяцию.

##  <a name="setduration"></a>Цинтерполаторбасе:: Сетдуратион

Задает длительность интерполяции

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*длитель*<br/>
Длительность перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, он возвращает значение S_OK. Он возвращает значение E_FAIL, если Ккустоминтерполатор не задано, или пользовательская реализация возвращает FALSE из метода Сетдуратион.

##  <a name="setinitialvalueandvelocity"></a>Цинтерполаторбасе:: СетинитиалвалуеандвелоЦити

Задает начальное значение и скорость для интерполяции.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Параметры

*инитиалвалуе*<br/>
Значение переменной в начале перехода.

*InitialVelocity равно*<br/>
Скорость переменной в начале перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается с ошибкой, он возвращает значение S_OK. Он возвращает значение E_FAIL, если Ккустоминтерполатор не задано, или пользовательская реализация возвращает FALSE из метода СетинитиалвалуеандвелоЦити.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
