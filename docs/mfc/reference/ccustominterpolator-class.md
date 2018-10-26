---
title: Класс CCustomInterpolator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
dev_langs:
- C++
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0c924f49d8b1ec00585c90d5e106a9f6446f521d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072854"
---
# <a name="ccustominterpolator-class"></a>Класс CCustomInterpolator

Реализует базовый интерполятор.

## <a name="syntax"></a>Синтаксис

```
class CCustomInterpolator;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|Перегружен. Создает объект пользовательского интерполятора и инициализирует длительность и скорость для указанных значений.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCustomInterpolator::GetDependencies](#getdependencies)|Возвращает зависимости интерполятор.|
|[CCustomInterpolator::GetDuration](#getduration)|Возвращает длительность интерполятор.|
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Получает конечное значение, к которому ведет интерполятора.|
|[CCustomInterpolator::Init](#init)|Инициализирует длительность и конечное значение.|
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Осуществляет интерполяцию значение с указанным смещением.|
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Осуществляет интерполяцию скорости, начиная с указанной позиции|
|[CCustomInterpolator::SetDuration](#setduration)|Задает длительность интерполятор.|
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Задает начальное значение и скорости интерполятор.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|Интерполированное значение.|
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|Интерполированные скорость.|
|[CCustomInterpolator::m_duration](#m_duration)|Длительность перехода.|
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|Конечное значение переменной в конце перехода.|
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|Значение переменной в начале перехода.|
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|Скорость, переменной в начале перехода.|

## <a name="remarks"></a>Примечания

Наследовать класс от CCustomInterpolator и переопределить все необходимые методы для реализации пользовательской интерполяция алгоритма. Указатель на этот класс должен передать как параметр CCustomTransition.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CCustomInterpolator`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="ccustominterpolator"></a>  CCustomInterpolator::CCustomInterpolator

Создает объект пользовательского интерполятора и задает все значения по умолчанию 0.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

*finalValue*

### <a name="remarks"></a>Примечания

Используйте CCustomInterpolator::Init для инициализации длительность и конечное значение далее в коде.

##  <a name="getdependencies"></a>  CCustomInterpolator::GetDependencies

Возвращает зависимости интерполятор.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Параметры

*initialValueDependencies*<br/>
Выходные данные. Аспекты интерполятора, которые зависят от начального значения, передаваемые от SetInitialValueAndVelocity.

*initialVelocityDependencies*<br/>
Выходные данные. Аспекты интерполятора, которые зависят от начальной скорости, передаваемые от SetInitialValueAndVelocity.

*durationDependencies*<br/>
Выходные данные. Аспекты интерполятора, которые зависят от длительности, передаваемые от SetDuration.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает значение TRUE. Возвращает значение FALSE из переопределенную реализацию, если вы хотите события сбоя.

##  <a name="getduration"></a>  CCustomInterpolator::GetDuration

Возвращает длительность интерполятор.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Выходные данные. Длительность перехода, в секундах.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает значение TRUE. Возвращает значение FALSE из переопределенную реализацию, если вы хотите события сбоя.

##  <a name="getfinalvalue"></a>  CCustomInterpolator::GetFinalValue

Получает конечное значение, к которому ведет интерполятора.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*значение*<br/>
Выходные данные. Конечное значение переменной в конце перехода.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает значение TRUE. Возвращает значение FALSE из переопределенную реализацию, если вы хотите события сбоя.

##  <a name="init"></a>  CCustomInterpolator::Init

Инициализирует длительность и конечное значение.

```
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

*finalValue*<br/>
Конечное значение переменной в конце перехода.

##  <a name="interpolatevalue"></a>  CCustomInterpolator::InterpolateValue

Осуществляет интерполяцию значение с указанным смещением.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*значение*<br/>
Выходные данные. Интерполированное значение.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает значение TRUE. Возвращает значение FALSE из переопределенную реализацию, если вы хотите события сбоя.

##  <a name="interpolatevelocity"></a>  CCustomInterpolator::InterpolateVelocity

Осуществляет интерполяцию скорости, начиная с указанной позиции

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>Параметры

*Скорость*<br/>
Выходные данные. Скорость переменной по смещению.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает значение TRUE. Возвращает значение FALSE из переопределенную реализацию, если вы хотите события сбоя.

##  <a name="m_currentvalue"></a>  CCustomInterpolator::m_currentValue

Интерполированное значение.

```
DOUBLE m_currentValue;
```

##  <a name="m_currentvelocity"></a>  CCustomInterpolator::m_currentVelocity

Интерполированные скорость.

```
DOUBLE m_currentVelocity;
```

##  <a name="m_duration"></a>  CCustomInterpolator::m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CCustomInterpolator::m_finalValue

Конечное значение переменной в конце перехода.

```
DOUBLE m_finalValue;
```

##  <a name="m_initialvalue"></a>  CCustomInterpolator::m_initialValue

Значение переменной в начале перехода.

```
DOUBLE m_initialValue;
```

##  <a name="m_initialvelocity"></a>  CCustomInterpolator::m_initialVelocity

Скорость, переменной в начале перехода.

```
DOUBLE m_initialVelocity;
```

##  <a name="setduration"></a>  CCustomInterpolator::SetDuration

Задает длительность интерполятор.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает значение TRUE. Возвращает значение FALSE из переопределенную реализацию, если вы хотите события сбоя.

##  <a name="setinitialvalueandvelocity"></a>  CCustomInterpolator::SetInitialValueAndVelocity

Задает начальное значение и скорости интерполятор.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>Параметры

*Начальное значение*<br/>
Значение переменной в начале перехода.

*initialVelocity*<br/>
Скорость, переменной в начале перехода.

### <a name="return-value"></a>Возвращаемое значение

Основные реализация всегда возвращает значение TRUE. Возвращает значение FALSE из переопределенную реализацию, если вы хотите события сбоя.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
