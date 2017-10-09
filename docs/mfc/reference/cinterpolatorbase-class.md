---
title: "Класс CInterpolatorBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 6bf2a6b11f64b5ec7e7f2e311c62e7f1ce9144d8
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cinterpolatorbase-class"></a>Класс CInterpolatorBase
Реализует обратный вызов, используемый API анимации, когда требуется рассчитать новое значение переменной анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Создает `CInterpolatorBase` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](#createinstance)|Создает экземпляр `CInterpolatorBase` и содержит указатель на пользовательские интерполятора, который будет обработки событий.|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|Возвращает интерполятора зависимости. (Переопределяет `CUIAnimationInterpolatorBase::GetDependencies`.)|  
|[CInterpolatorBase::GetDuration](#getduration)|Возвращает продолжительность интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::GetDuration`.)|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Возвращает конечное значение, к которому ведет интерполятора. (Переопределяет `CUIAnimationInterpolatorBase::GetFinalValue`.)|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Выполняет интерполяцию значение с указанным смещением (переопределяет `CUIAnimationInterpolatorBase::InterpolateValue`.)|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Выполняет интерполяцию скорости, с указанным смещением (переопределяет `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Содержит указатель на пользовательские интерполятора, который будет обработки событий.|  
|[CInterpolatorBase::SetDuration](#setduration)|Задает продолжительность интерполятора (переопределяет `CUIAnimationInterpolatorBase::SetDuration`.)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Задает начальное значение интерполятора и скорости. (Переопределяет `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|  
  
## <a name="remarks"></a>Примечания  
 Создается и передается в этот обработчик `IUIAnimationTransitionFactory::CreateTransition` при `CCustomTransition` объект создается как часть процесса инициализации анимации (запущенную `CAnimationController::AnimateGroup`). Обычно использовать его напрямую не требуется, просто перенаправляет вызвавший все события для `CCustomInterpolator`-производного класса, указатель передается в конструктор этого `CCustomTransition`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="cinterpolatorbase"></a>CInterpolatorBase::CInterpolatorBase  
 Создает объект CInterpolatorBase.  
  
```  
CInterpolatorBase();
```  
  
##  <a name="createinstance"></a>CInterpolatorBase::CreateInstance  
 Создает экземпляр CInterpolatorBase и сохраняет указатель на пользовательские интерполятора, который будет обработки событий.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,  
    IUIAnimationInterpolator** ppHandler);
```  
  
### <a name="parameters"></a>Параметры  
 `pInterpolator`  
 Указатель на пользовательские интерполятор.  
  
 `ppHandler`  
 Выходные данные. Содержит указатель на экземпляр CInterpolatorBase при возврате из функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="getdependencies"></a>CInterpolatorBase::GetDependencies  
 Возвращает интерполятора зависимости.  
  
```  
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>Параметры  
 `initialValueDependencies`  
 Выходные данные. Интерполятора аспекты, которые зависят от начального значения, передаваемые SetInitialValueAndVelocity.  
  
 `initialVelocityDependencies`  
 Выходные данные. Интерполятора аспекты, которые зависят от начальной скоростью передан SetInitialValueAndVelocity.  
  
 `durationDependencies`  
 Выходные данные. Аспекты интерполятора, зависящих от длительности передан SetDuration.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не заданы, или пользовательские реализации возвращает значение FALSE из метода GetDependencies.  
  
##  <a name="getduration"></a>CInterpolatorBase::GetDuration  
 Возвращает продолжительность интерполятор.  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Выходные данные. Продолжительность перехода в секундах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не заданы, или пользовательские реализации возвращает значение FALSE из метода GetDuration.  
  
##  <a name="getfinalvalue"></a>CInterpolatorBase::GetFinalValue  
 Возвращает конечное значение, к которому ведет интерполятора.  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>Параметры  
 `value`  
 Выходные данные. Конечное значение переменной в конце перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не заданы, или пользовательские реализации возвращает значение FALSE из метода GetFinalValue.  
  
##  <a name="interpolatevalue"></a>CInterpolatorBase::InterpolateValue  
 Выполняет интерполяцию значение с указанным смещением  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>Параметры  
 `offset`  
 Смещение от начала перехода. Смещение всегда больше или равно нулю и меньше, чем продолжительность для перехода. Этот метод не вызывается, если продолжительность перехода равно нулю.  
  
 `value`  
 Выходные данные. Интерполированное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не заданы, или пользовательские реализации возвращает значение FALSE из метода InterpolateValue.  
  
##  <a name="interpolatevelocity"></a>CInterpolatorBase::InterpolateVelocity  
 Выполняет интерполяцию скорости, начиная с указанной позиции  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Параметры  
 `offset`  
 Смещение от начала перехода. Смещение всегда больше или равно нулю и меньше или равно длительности перехода. Этот метод не вызывается, если продолжительность перехода равно нулю.  
  
 `velocity`  
 Выходные данные. Скорость переменной с позиции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не заданы, или пользовательские реализации возвращает значение FALSE из метода InterpolateVelocity.  
  
##  <a name="setcustominterpolator"></a>CInterpolatorBase::SetCustomInterpolator  
 Содержит указатель на пользовательские интерполятора, который будет обработки событий.  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Параметры  
 `pInterpolator`  
 Указатель на пользовательские интерполятор.  
  
##  <a name="setduration"></a>CInterpolatorBase::SetDuration  
 Задает продолжительность интерполятора  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Продолжительность перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не заданы, или пользовательские реализации возвращает значение FALSE из метода SetDuration.  
  
##  <a name="setinitialvalueandvelocity"></a>CInterpolatorBase::SetInitialValueAndVelocity  
 Задает начальное значение интерполятора и скорости.  
  
```  
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue, 
  __in DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Параметры  
 `initialValue`  
 Значение переменной в начале перехода.  
  
 `initialVelocity`  
 Скорость переменной в начале перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не заданы, или пользовательские реализации возвращает значение FALSE из метода SetInitialValueAndVelocity.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

