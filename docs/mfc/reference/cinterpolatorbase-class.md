---
title: "Класс CInterpolatorBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CInterpolatorBase class
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 44c67eef38b34a2a3cf677b42a40304c01668b42
ms.lasthandoff: 02/24/2017

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
|[CInterpolatorBase::CreateInstance](#createinstance)|Создает экземпляр `CInterpolatorBase` и сохраняет указатель на пользовательские интерполятор, который будет обрабатывать события.|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|Возвращает зависимости интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::GetDependencies`.)|  
|[CInterpolatorBase::GetDuration](#getduration)|Возвращает длительность интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::GetDuration`.)|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Возвращает последнее значение, к которому ведет интерполятора. (Переопределяет `CUIAnimationInterpolatorBase::GetFinalValue`.)|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Выполняет интерполяцию значение с указанным смещением (переопределяет `CUIAnimationInterpolatorBase::InterpolateValue`.)|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Выполняет интерполяцию скорости с указанным смещением (переопределяет `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Хранит указатель на пользовательские интерполятор, который будет обрабатывать события.|  
|[CInterpolatorBase::SetDuration](#setduration)|Задает продолжительность интерполятор (переопределяет `CUIAnimationInterpolatorBase::SetDuration`.)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Задает начальное значение и скорости интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|  
  
## <a name="remarks"></a>Примечания  
 Этот обработчик создается и передается `IUIAnimationTransitionFactory::CreateTransition` при `CCustomTransition` объект создается как часть процесса инициализации анимации (начатую `CAnimationController::AnimateGroup`). Обычно не нужно использовать этот класс непосредственно, просто перенаправляет вызвавший все события для `CCustomInterpolator`-производного класса, указатель, переданный в конструктор `CCustomTransition`.  
  
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
 Создает экземпляр CInterpolatorBase и сохраняет указатель на пользовательские интерполятор, который будет обрабатывать события.  
  
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
 Возвращает зависимости интерполятор.  
  
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
 Выходные данные. Интерполятора аспекты, которые зависят от начальной скорости, передаваемые SetInitialValueAndVelocity.  
  
 `durationDependencies`  
 Выходные данные. Аспекты интерполятора, зависящие от длительности, передаваемые SetDuration.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. E_FAIL возвращается, если CCustomInterpolator не задано или пользовательскую реализацию метода GetDependencies возвращает значение FALSE.  
  
##  <a name="getduration"></a>CInterpolatorBase::GetDuration  
 Возвращает длительность интерполятор.  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Выходные данные. Продолжительность перехода в секундах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. E_FAIL возвращается, если CCustomInterpolator не задано или пользовательскую реализацию метода GetDuration возвращает значение FALSE.  
  
##  <a name="getfinalvalue"></a>CInterpolatorBase::GetFinalValue  
 Возвращает последнее значение, к которому ведет интерполятора.  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>Параметры  
 `value`  
 Выходные данные. Конечное значение переменной в конце перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. E_FAIL возвращается, если CCustomInterpolator не задано или пользовательскую реализацию метода GetFinalValue возвращает значение FALSE.  
  
##  <a name="interpolatevalue"></a>CInterpolatorBase::InterpolateValue  
 Выполняет интерполяцию значение с указанным смещением  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>Параметры  
 `offset`  
 Смещение от начала перехода. Смещение всегда больше или равно нулю и меньше, чем продолжительность перехода. Этот метод не вызывается, если длительность перехода равно нулю.  
  
 `value`  
 Выходные данные. Интерполированное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. E_FAIL возвращается, если CCustomInterpolator не задано или пользовательскую реализацию метода InterpolateValue возвращает значение FALSE.  
  
##  <a name="interpolatevelocity"></a>CInterpolatorBase::InterpolateVelocity  
 Выполняет интерполяцию скорости, начиная с указанной позиции  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Параметры  
 `offset`  
 Смещение от начала перехода. Смещение всегда больше или равно нулю и меньше или равно длительности перехода. Этот метод не вызывается, если длительность перехода равно нулю.  
  
 `velocity`  
 Выходные данные. Скорость смещение переменной.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. E_FAIL возвращается, если CCustomInterpolator не задано или пользовательскую реализацию метода InterpolateVelocity возвращает значение FALSE.  
  
##  <a name="setcustominterpolator"></a>CInterpolatorBase::SetCustomInterpolator  
 Хранит указатель на пользовательские интерполятор, который будет обрабатывать события.  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Параметры  
 `pInterpolator`  
 Указатель на пользовательские интерполятор.  
  
##  <a name="setduration"></a>CInterpolatorBase::SetDuration  
 Задает продолжительность интерполятор  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Длительность перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. E_FAIL возвращается, если CCustomInterpolator не задано или пользовательскую реализацию метода SetDuration возвращает значение FALSE.  
  
##  <a name="setinitialvalueandvelocity"></a>CInterpolatorBase::SetInitialValueAndVelocity  
 Задает начальное значение и скорости интерполятор.  
  
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
 Если метод завершается успешно, возвращается значение S_OK. E_FAIL возвращается, если CCustomInterpolator не задано или пользовательскую реализацию метода SetInitialValueAndVelocity возвращает значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

