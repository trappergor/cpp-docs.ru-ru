---
title: "CAccelerateDecelerateTransition Class1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f11dc96b48695b998fb17c33735e8f56bce517b7
ms.lasthandoff: 02/24/2017

---
# <a name="cacceleratedeceleratetransition-class"></a>Класс CAccelerateDecelerateTransition
Реализует переход между ускорением и замедлением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Создает объект перехода.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](#create)|Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Отношение времени, затраченный на ускорение длительности.|  
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Отношение времени, затраченный на замедление длительности.|  
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Длительность перехода.|  
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Значение переменной анимации в конце перехода.|  
  
## <a name="remarks"></a>Примечания  
 Во время ускорением-Замедление перехода, переменной анимации ускоряет и затем замедляет работу на протяжении перехода заканчивается на указанное значение. Можно управлять как быстро переменной ускоряется и независимо друг от друга, замедляется, указав другой ускорение и замедление коэффициенты. Если Начальная скорость равен нулю, ускорение составляет долю времени, на которое переменную потратит ускорение; Аналогичным образом с коэффициентом замедление. Начальная скорость не равно нулю, при долю времени между скорости, достигло нуля до окончания перехода. Коэффициент ускорение и замедление отношение должно быть равно более 1.0. Поскольку автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока затем возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CAccelerateDecelerateTransition`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-namecacceleratedeceleratetransitiona--cacceleratedeceleratetransitioncacceleratedeceleratetransition"></a><a name="cacceleratedeceleratetransition"></a>CAccelerateDecelerateTransition::CAccelerateDecelerateTransition  
 Создает объект перехода.  
  
```  
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE accelerationRatio = 0.3,  
    DOUBLE decelerationRatio = 0.3);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Длительность перехода.  
  
 `finalValue`  
 Значение переменной анимации в конце перехода.  
  
 `accelerationRatio`  
 Отношение времени, затраченный на ускорение длительности.  
  
 `decelerationRatio`  
 Отношение времени, затраченный на замедление длительности.  
  
##  <a name="a-namecreatea--cacceleratedeceleratetransitioncreate"></a><a name="create"></a>CAccelerateDecelerateTransition::Create  
 Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* *\not used*\);
```  
  
### <a name="parameters"></a>Параметры  
`pLibrary`  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), определяющего библиотеки стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создано успешно; в противном случае — значение FALSE.  
  
##  <a name="a-namemaccelerationratioa--cacceleratedeceleratetransitionmaccelerationratio"></a><a name="m_accelerationratio"></a>CAccelerateDecelerateTransition::m_accelerationRatio  
 Отношение времени, затраченный на ускорение длительности.  
  
```  
DOUBLE m_accelerationRatio;  
```  
  
##  <a name="a-namemdecelerationratioa--cacceleratedeceleratetransitionmdecelerationratio"></a><a name="m_decelerationratio"></a>CAccelerateDecelerateTransition::m_decelerationRatio  
 Отношение времени, затраченный на замедление длительности.  
  
```  
DOUBLE m_decelerationRatio;  
```  
  
##  <a name="a-namemdurationa--cacceleratedeceleratetransitionmduration"></a><a name="m_duration"></a>CAccelerateDecelerateTransition::m_duration  
 Длительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="a-namemfinalvaluea--cacceleratedeceleratetransitionmfinalvalue"></a><a name="m_finalvalue"></a>CAccelerateDecelerateTransition::m_finalValue  
 Значение переменной анимации в конце перехода.  
  
```  
DOUBLE m_finalValue;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

