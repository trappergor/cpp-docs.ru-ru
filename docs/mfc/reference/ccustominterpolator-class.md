---
title: "Класс CCustomInterpolator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 4198e4b694356087cccad99d8ca62da3f23ba6ec
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="ccustominterpolator-class"></a>Класс CCustomInterpolator
Реализует базовый интерполятор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCustomInterpolator;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|Перегружен. Создает объект пользовательского интерполятора и инициализирует длительность и скорости указанные значения.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCustomInterpolator::GetDependencies](#getdependencies)|Возвращает интерполятора зависимости.|  
|[CCustomInterpolator::GetDuration](#getduration)|Возвращает продолжительность интерполятор.|  
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Возвращает конечное значение, к которому ведет интерполятора.|  
|[CCustomInterpolator::Init](#init)|Инициализирует длительность и конечное значение.|  
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Выполняет интерполяцию значение с указанным смещением.|  
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Выполняет интерполяцию скорости, начиная с указанной позиции|  
|[CCustomInterpolator::SetDuration](#setduration)|Задает продолжительность интерполятор.|  
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Задает начальное значение интерполятора и скорости.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|Интерполированное значение.|  
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|Интерполированные скорости.|  
|[CCustomInterpolator::m_duration](#m_duration)|Продолжительность перехода.|  
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|Конечное значение переменной в конце перехода.|  
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|Значение переменной в начале перехода.|  
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|Скорость переменной в начале перехода.|  
  
## <a name="remarks"></a>Примечания  
 Создайте класс, производный от CCustomInterpolator и переопределять все методы, необходимые для реализации алгоритма пользовательских интерполяции. Указатель на этот класс должны передаваться как параметр CCustomTransition.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CCustomInterpolator`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="ccustominterpolator"></a>CCustomInterpolator::CCustomInterpolator  
 Создает объект пользовательского интерполятора и задает все значения по умолчанию 0.  
  
```  
CCustomInterpolator();

 
CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Продолжительность перехода.  
  
 `finalValue`  
  
### <a name="remarks"></a>Примечания  
 С помощью CCustomInterpolator::Init инициализировать длительность и конечное значение далее в коде.  
  
##  <a name="getdependencies"></a>CCustomInterpolator::GetDependencies  
 Возвращает интерполятора зависимости.  
  
```  
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,  
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,  
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>Параметры  
 `initialValueDependencies`  
 Выходные данные. Интерполятора аспекты, которые зависят от начального значения, передаваемые SetInitialValueAndVelocity.  
  
 `initialVelocityDependencies`  
 Выходные данные. Интерполятора аспекты, которые зависят от начальной скоростью передан SetInitialValueAndVelocity.  
  
 `durationDependencies`  
 Выходные данные. Аспекты интерполятора, зависящих от длительности передан SetDuration.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовая реализация всегда возвращает значение TRUE. Возвращают FALSE из переопределенная реализация, при желании сбой события.  
  
##  <a name="getduration"></a>CCustomInterpolator::GetDuration  
 Возвращает продолжительность интерполятор.  
  
```  
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Выходные данные. Продолжительность перехода в секундах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовая реализация всегда возвращает значение TRUE. Возвращают FALSE из переопределенная реализация, при желании сбой события.  
  
##  <a name="getfinalvalue"></a>CCustomInterpolator::GetFinalValue  
 Возвращает конечное значение, к которому ведет интерполятора.  
  
```  
virtual BOOL GetFinalValue(DOUBLE* value);
```  
  
### <a name="parameters"></a>Параметры  
 `value`  
 Выходные данные. Конечное значение переменной в конце перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовая реализация всегда возвращает значение TRUE. Возвращают FALSE из переопределенная реализация, при желании сбой события.  
  
##  <a name="init"></a>CCustomInterpolator::Init  
 Инициализирует длительность и конечное значение.  
  
```  
void Init(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Продолжительность перехода.  
  
 `finalValue`  
 Конечное значение переменной в конце перехода.  
  
##  <a name="interpolatevalue"></a>CCustomInterpolator::InterpolateValue  
 Выполняет интерполяцию значение с указанным смещением.  
  
```  
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* value);
```  
  
### <a name="parameters"></a>Параметры  
 `value`  
 Выходные данные. Интерполированное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовая реализация всегда возвращает значение TRUE. Возвращают FALSE из переопределенная реализация, при желании сбой события.  
  
##  <a name="interpolatevelocity"></a>CCustomInterpolator::InterpolateVelocity  
 Выполняет интерполяцию скорости, начиная с указанной позиции  
  
```  
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Параметры  
 `velocity`  
 Выходные данные. Скорость переменной с позиции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовая реализация всегда возвращает значение TRUE. Возвращают FALSE из переопределенная реализация, при желании сбой события.  
  
##  <a name="m_currentvalue"></a>CCustomInterpolator::m_currentValue  
 Интерполированное значение.  
  
```  
DOUBLE m_currentValue;  
```  
  
##  <a name="m_currentvelocity"></a>CCustomInterpolator::m_currentVelocity  
 Интерполированные скорости.  
  
```  
DOUBLE m_currentVelocity;  
```  
  
##  <a name="m_duration"></a>CCustomInterpolator::m_duration  
 Продолжительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>CCustomInterpolator::m_finalValue  
 Конечное значение переменной в конце перехода.  
  
```  
DOUBLE m_finalValue;  
```  
  
##  <a name="m_initialvalue"></a>CCustomInterpolator::m_initialValue  
 Значение переменной в начале перехода.  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>CCustomInterpolator::m_initialVelocity  
 Скорость переменной в начале перехода.  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="setduration"></a>CCustomInterpolator::SetDuration  
 Задает продолжительность интерполятор.  
  
```  
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Продолжительность перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Базовая реализация всегда возвращает значение TRUE. Возвращают FALSE из переопределенная реализация, при желании сбой события.  
  
##  <a name="setinitialvalueandvelocity"></a>CCustomInterpolator::SetInitialValueAndVelocity  
 Задает начальное значение интерполятора и скорости.  
  
```  
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,  
    DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Параметры  
 `initialValue`  
 Значение переменной в начале перехода.  
  
 `initialVelocity`  
 Скорость переменной в начале перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Основные реализация всегда возвращает значение TRUE. Возвращают FALSE из переопределенная реализация, при желании сбой события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

